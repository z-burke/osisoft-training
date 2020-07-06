@snap[west]
## PI AF Best Practices
@snapend

+++

### Store the Data Archive Name as an Attribute
@snap[content]
@snap[flex-10]
@ul[](false)
- Using the substitution syntax *%Server%* will take the **client machine’s default Data Archive**.
    - This can cause problems when multiple Data Archives are being referenced in one hierarchy.
- Instead, store the target **Data Archive’s name as an attribute** and reference there.
- Consider using a **“Server Info”** element at the root of the hierarchy.
    - Can define Data Archive name.
    - Can define time zone.
    - Etc.
@ulend
@snapend
@snapend

+++

### Associate Every Element to a Template
@snap[content]
@snap[flex-10]
@ul[](false)
- Templates make AF much easier to manage at scale.<br>…but having a **mix of template-based and standalone elements creates confusion** and can make management difficult.
- For this reason, we have **every element associated with a template**, even if there will be only one element for a given template.
@ulend
@snapend
@snapend

+++

### Never Allow Extensions to Templates!
@snap[content]
@snap[flex-10]
@ul[](false)
- Allowing extensions to templates allows attributes to be defined in **both the template and directly within the element**.
    - Difficult to track where attributes are coming from.
    - Can lose data if someone “resets to template”
- If an attribute is truly unique to an element, **create another child template**, instead.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-template-extensions.png)
@snapend
@snapend

+++

### Don't Create Large AF Tables
@snap[content]
@snap[flex-10]
@ul[](false)
- Every time a table is accessed, the entire table must be loaded.
- Best practice is to keep tables to less than **10,000 rows**.
@ulend
@snapend
@snapend

+++

### Mapping Tags to Attributes - Other Strategies
@snap[content]
@snap[flex-10]
@ul[](false)
- Store tag names in an **AF Table**
    - Can pose problems if the table contains more than 10,000 tags.
- Store tag names in a **SQL database**.
    - Adds significant complexity to infrastructure.
- Store tag names as **child attributes** of the attribute meant to read from them.
    - Better, but can clutter up an already large collection of attributes.
- **Directly define** these data references for each attribute.
    - Even though a template may constrain what attributes exist, each one can be told to look at a different tag at the element level.
    - Can directly attach point names to attributes using PI Builder.
    - **Arguably the most scalable and easiest to manage**.
@ulend
@snapend
@snapend

+++

### Use More Analyses with Fewer Variables
@snap[content]
@snap[flex-10]
@ul[](false)
- Try to create analyses that only do “one thing” (i.e. are **mapped to one output attribute**.)
    - Makes it easier to understand what analyses actually do.
    - Finer control over analysis triggering
- Tradeoff: sometimes we group calculations together to **avoid recreating the same variables**.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-analysis-shared-variables.png)
@snapend
@snapend

+++

### Analysis Triggering
@snap[content]
@snap[flex-10]
@ul[](false)
- Analyses should only run **as frequently as needed**.
    - Typically range between once every 15 seconds to once every 24 hours.
- Be wary of having analyses trigger on **any input**.
    - Input data may update faster than predicted, causing the analysis to trigger more often than intended.
- Especially important to consider for roll-ups, which can cause a trigger to **cascade** up and down a hierarchy.
@ulend
@snapend
@snapend

+++

### Store Results of Analyses in PI Points
@snap[content]
@snap[flex-10]
@ul[](false)
- If an attribute is populated by an analysis, the analysis will be **rerun every time that attribute is referenced**.
    - All its input attributes will need to be resolved as well.
    - Causes a much heavier load on the analysis service.
- Whenever possible, **any attribute that gets its data from an analysis should be given a PI Point to reference**.
    - This causes the analysis to write its output directly to the referenced PI Point.
    - Every time the attribute is referenced, it will draw its data from this PI Point rather than rerunning the analysis.
@ulend
@snapend
@snapend

+++

### Checking for Bad Values in Analyses
@snap[content]
@snap[flex-10]
@ul[](false)
- **Real data has gaps** in it that can cause analyses to:
    - Produce nonsensical data.
    - Propagate errors.
- Avoid this by checking inconsistent inputs using the **BadVal** function.
@ulend
```excel zoom-12
If (BadVal('InputAttribute')
Then // Do Something
Else NoOutput()
```
@snapend
@snapend

+++

### Perform Analyses Close to Source, Reference Elsewhere
@snap[content]
@snap[flex-10]
@ul[](false)
- If an analysis needs to be created that runs only on data in a spot deeper in the hierarchy, **try to create the analysis at a lower level, then reference it from upper levels**.
- Avoids inadvertently recreating analyses in multiple areas of the hierarchy.
- Better **communicates intent**.
@snapend
@snapend

+++

### Auditing Analysis Performance - Viewing Statistics
@snap[content]
@snap[flex-10]
@ul[](false)
- Right-clicking on the Operations panel from within the Management tab provides access **to analysis service statistics**.
- Statistics are gathered since the last time the analysis service (or the machine it’s on) is reset.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-analysis-statistics.png)
@snapend
@snapend

+++

### Auditing Analysis Performance - Viewing Statistics
@snap[content]
@snap[flex-10]
@ul[](false)
- Right-clicking on the Operations panel from within the Management tab provides access **to analysis service statistics**.
- Statistics are gathered since the last time the analysis service (or the machine it’s on) is reset.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-analysis-statistics.png)
@snapend
@snapend

+++

### Auditing Analyses Performance - Statistics Menu
@snap[content]
@snap[flex-10]
@ul[](false)
- Can see statistics for each analysis:
    - **AverageLagMilliSeconds**: Amount of time between when an analysis is triggered and when it produces an output (input resolution and exectuion).
    - **AverageElapsedMilliSeconds**: Amount of time it takes for analysis to execute once its inputs have been resolved.
    - **AverageTriggerMilliSeconds**: How often (on average) an analysis is asked to run.
- Load shedding kicks in when TriggerMilliSeconds is greater than LagMilliSeconds.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-analysis-statistics-menu.png)
@snapend
@snapend

+++

### Managing Tag Creation and Config Through AF Tempaltes
@snap[content]
@snap[flex-10]
@ul[](false)
- If creating PI Points based on a template, **substitution syntax can be used to define their names** in the context of the elements they pertain to.
- Tags can also be configured in this manner. Substitution syntax **can be used to define configuration parameters for the PI Point**. 
- Provides an easy and powerfully **declarative** way or managing PI Points.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-template-tag-creation.png)
@snapend
@snapend

+++

### Duration of Event Frames
@snap[content]
@snap[flex-10]
@ul[](false)
- Event Frames can cause performance for the analysis service if they last longer than **2 weeks**.
- Can set up an Event Frame search in AF to make finding these easier
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-eventframe-duration.png)
@snapend
@snapend

+++

### Duration of Event Frames
@snap[content]
@snap[flex-10]
@ul[](false)
- Event Frames can cause performance for the analysis service if they last longer than **2 weeks**.
- Can set up an Event Frame search in AF to make finding these easier
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-eventframe-duration.png)
@snapend
@snapend

+++

### Use Notifications Conservatively
@snap[content]
@snap[flex-10]
@ul[](false)
- AF Notifications lose their effectiveness if they are triggered too frequently.
    - Depends on context, **but even 2x / week can be too much**.
- Notifications are based on Event Frames, which **can be generated excessively when data is fluctuating**.
    - Keep this in mind when building a Notification Rule.
@snapend
@snapend