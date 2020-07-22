@snap[west]
## AF Analytics
@snapend

+++

### PI AF Analyses
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
AF Analyses allows us to calculate **strategic data** in real-time.
<br>
It can store the results of these calculations in **PI Points** right alongside operational data.
@snapend
@snapend
+++

### Analyses vs. Forumulas
@snap[content flex-10]
@snap[flex-10]
Analyses:
@ul[text-11](false)
- provide a more **powerful syntax**.
- have more powerful **tools for management**.
- can be configured to run at set **intervals**.
- can **historize data** (write to PI Points).
@ulend
@snapend
@snapend


+++

### 4 Types of Analyses
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Expressions
- Rollups
- Event Frame Generation
- SQC
@ulend
@snapend
@snap[flex-16 flex-center]
![](assets/img/pse-analyses-types.png)
@snapend
@snapend

+++

### Expressions
@snap[content]
@snap[flex-10]
Can perform calculations whose results are **output to attributes**.
@ul[](false)
- Can historize outputs (if output Attributes are configured to do so)
- Utilizes an easy, Excel formula-like syntax
- Includes a collection of powerful functions
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-expressions.png)
@snapend
@snapend

+++

### Rollups
@snap[content flex-10]
@snap[flex-10]
Can perform calculations on a **variable number of child elements** such as:
@ul[](false)
- Sum
- Average
- Min/Max
Like expressions, rollups can output their results to PI Points (via Attributes mapped to them).
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-rollup.png)
@snapend

+++

### Event Frames

@snap[content flex-center]
@snap[flex-10]
Provide a way to **“bookmark”** interesting points of time (events).
@ul[](false)
- Are generated based on a defined set of **triggers**.
- Can collect Attributes of interest using Event Frame Templates.
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-eventframes.png)
@snapend
@snapend

+++

### SQC (Statistical Quality Control)
@snap[content]
@snap[flex-10]
Defines allowable **deviances** from a desired **operating range** of an attribute.
These can be recorded to:
@ul[](false)
- Event Frames
- PI Points (via Attribute mappings)
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-sqc.png)
@snapend
@snapend
@snap[content]
@snap[flex-10 text-center]
These are less commonly used and therefore **will not be covered** in this course.
@snapend
@snapend

+++

### How Expression Analyses are Structured
@snap[content]
@snap[flex-10]
Each Analysis of an **expression** type:
@ol[](false)
1. Can consist of **several** expressions:
    1. Each outputs to a variable accessible to other expressions with the Analysis
    1. Variables can be mapped to output Attributes
1. Is **started/stopped** as a unit
1. Collectively runs at a configurable **frequency**
@olend
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-expression.png)
@snapend
@snapend

+++

### Exercise: Creating an Analysis Expression
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-creating-analysis-expression.gif)
@css[text-07](Every 5 minutes, this analysis will generate a random value between -20 and 30 and another that is always 2 more than that one.)
@snapend
@snapend

+++

### Expressions: Syntax

Expressions use a syntax similar to Excel formulas.
<br><br>
```excel zoom-12
Int('*'- ParseTime(Concat("T +",Hour('*'),"h")))/60

'Height'/100 * (If RawLevel < 0 then 0
    else if RawLevel > 100 then 100
        else RawLevel)
```
<br>
**Int** is a function (along with others like **ParseTime** and **Concat**)
<br>
**"..."** will evaluate to a string.
<br>
**'...'** is a reference to an attribute or a point in time.

+++

### Expressions: Some Useful Functions
@snap[content]
@ul[text-09](false)
- **Badval:** Test a value to see if it’s bad.
- **Convert:** Convert a value from its current UOM to a specified UOM.
- **DigState:** Convert a string to a corresponding PI Data Archive digital state object.
- **NoOutput:** Do not write current calculation result.
- **ParseTime:** Translate a PI time expression to a timestamp.
- **PctGood:** Find the time percentage for which the attribute had good values.
- **PrevVal:** Find the last recorded value before a specified time.
- **Rand:** Return a random number.
- **TagAvg:** Find the time-weighted average of values for an attribute during a specified time range.
- **TagTot:** Find the totalized value (time integral) of a specified time range.
- **TagVal:** Return the value of an attribute at a specified time.
- *Also comes with useful functions for steam!*

+++

### Expressions: Function Help
@snap[content]
@snap[flex-10]
AF provides two sources of help for using Expressions:
@ul[](false)
- In the **Functions** panel in the bottom right hand corner.
- As **pop-up dialogues** that appear in real-time as expressions are being written (similar to Intellisense)
@ulend
Both of these provide function **descriptions** and **instructions for use**.
@snapend
@snap[flex-10 text-center]
![](assets/img/pse-function-help.png)
@snapend

+++

### Evaluating Expressions
@snap[content flex-10]
@snap[flex-10]
The **Evaluate** button provides a way for us to preview what the output(s) of our analysis will be.
@ol[](false)
1. Select an **Example Element**
1. Click the **Evaluate** button
1. An output value will appear for each expression
@olend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-analysis-expression-evaluate.png)
@snapend

+++

### Exercise: Evaluating an Expression
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-evaluating-analysis-expression.gif)
@css[text-07]()
@snapend
@snapend

+++

### Expressions: Help Referencing Attributes
@snap[content]
@snap[flex-10]
Referencing attributes can be tricky.
The help panel also gives us a way of **finding references** to specific attributes.
@ul[](false)
- Absolute paths
- Relative paths
@ulend
@snapend
@snap[flex-10 text-center]
![](assets/img/pse-analysis-attribute-help.png)
@snapend
@snapend

+++

### Exercise: Attribute as an Expression Input
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-analysis-expression-input-attribute.gif)
@css[text-07]()
@snapend
@snapend

+++

### Event Frames - Triggering
@snap[content]
@snap[flex-10]
Event frames start when a **Start Trigger** is **true** for a set period of time and will end when an **End Trigger** is **true**.
An End Trigger doesn't have to be defined...
@snapend
@snapend
@snap[content]
@snap[flex-10 text-right]
... the Event Frame will end when when the Start Trigger<br>is **no longer true**.
@snapend
@snapend
@snap[content flex-10]
@snap[flex flex-center]
![](assets/img/pse-eventframe-trigger.png)
@snapend
@snapend

+++

### Event Frames - Templates

@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Event Frame Templates specify:
    - What **attributes** should be associated with an Event Frame
    - What **naming scheme** Event Frames should follow when they are generated.
- Event Frames analyses cannot be defined without a template!
    - The template can be empty… it **just has to exist**!
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-eventframe-templates.png)
@snapend
@snapend

+++

### Viewing Recorded Event Frames
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Recorded Event Frames can be viewed from the **Event Frames** tab in System Explorer.
- Can perform searches to filter results.
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-eventframe-list.png)
@snapend
@snapend

+++

### Triggering Analyses
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Analyses can trigger based on two types of triggers:
    - **Periodic**: Runs at a set interval.
    - **Event-Triggered**: Runs when it detects a change in inputs.<br>(Can select which inputs can act as a trigger.)
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-analysis-triggering.png)
@snapend

+++

### Backfilling
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- What happens if we make a change an analysis?
    - There will be an artificial **inflection point** in the data from the moment of change!
- We can have an analysis rewrite tag history / recreate Event Frames by **backfilling**.
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-analysis-backfilling.png)
@snapend
@snapend

+++

### Managing Analyses
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- A list of all analyses in an AF database can be found in the Management tab.
- Can filter view based on search criteria.
- Can turn analyses on/off, backfill them.
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-managing-analyses.png)
@snapend
@snapend

+++

### Creating Output PI Points for Analysis Attributes
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- PI AF can create referenced PI Points.
- Attribute’s data reference settings become PI Point’s configuration.
- Incredibly powerful when used with templates. Very often used to contain outputs from analyses.
- Triggered by<br>**“Create or Update PI Point”**
@ulend
@snapend
@snap[flex-10 flex-center]
![height=500](assets/img/pse-analysis-create-pi-point.png)
@snapend
@snapend

+++

### Analyses and Templates
- Consider leaving Analyses off until explicitly enabled (alllows for testing)
- It's technically possible to create analyses at the Element level (instead of the Template). However, this is not recommended. If Elements of the same Template have the same Attributes, why not calculate the same thing?

+++

### Beyond AF Analytics
@snap[content]
@snap[flex-10]
AF Analyses strike a balance between power and manageability. But can also be somewhat limiting. What happens if we want to perform calculations that:
@ul[](false)
- Use functions **not provided** to us via AF?
- Leverage **machine learning**?
- Are extremely **resource intensive** and are best kept separate?
@ulend
@snapend
@snapend

+++

### Beyond AF Analytics
@snap[content]
@snap[flex-10]
When AF Analytics are not enough, we can read from and write back to the PI System through two different pathways:
@ul[](false)
- **PI Web API**: Provides read/write access to PI data over the web (http).
- **AFSDK**: Provides programmatic access to PI data and PI System configuration locally.
@ulend
While this can be a lot more to manage, it gives us the benefit of much more freedom!
@snapend
@snapend