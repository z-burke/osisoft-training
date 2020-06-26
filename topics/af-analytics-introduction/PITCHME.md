@snap[west]
## AF Analytics - Introduction
@snapend

+++

### Two Types of Data
@snap[content]
@snap[content-10]
**Operational**
@ul[](false)
- Directly measurable quantities
- Physical, "no undo"
- i.e. Sensor readings
    - Flow rate
    - Temperature
@ulend
@snapend
@snap[content-10]
**Strategic**
@ul[](false)
- Calculated quantities
- Abstract, "can undo"
- Calcluated from operational data
- i.e. KPI's
    - OEE
    - Production over time
@ulend
@snapend
@snapend

+++


### PI AF Analyses
@snap[midpoint span-100]
<br>
AF Analyses allows us to calculate **strategic data** in real-time.
<br>
It can store the results of these calculations in **PI Points** right alongside operational data.
@snapend

+++

### Analyses vs. Forumulas
@snap[content]
@snap[content-10]
Analyses:
@ul[](false)
- provide a more **powerful syntax**.
- have more powerful **tools for management**.
- can be configured to run at set **intervals**.
- can **historize data** (wrte to PI Points).
@ulend
@snapend
@snapend


+++

### 4 Types of Analyses
@snap[content]
@snap[content-10]
@ul[](false)
- Expressions
- Rollups
- Event Frame Generation
- SQC
@ulend
@snapend
@snap[content-15 flex-center-y]
![](assets\img\pse-analyses-types.png)
@snapend
@snapend

+++

### Expressions
@snap[content]
@snap[content-10]
Can perform calculations whose results are **output to attributes**.
<br>
@css[text-08]((Will write to a PI Point if the attribute has a PI Point Data Reference.))
@snapend
@snap[content-10 flex-center-y]
![](assets\img\pse-expressions.png)
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
"..." will evaluate to a string.
<br>
'...' is a reference to an attribute or a point in time.

+++

### Expressions: Some Useful Functions
@snap[content]
@ul[](false)
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
- *Also comes with many useful functions for steam!*

+++

### Expressions Included Function Help
@snap[content]
@snap[content-10]
All of the functions available available to use are listed in the panel at the bottom-right hand corner of the screen.
<br>
Also **provides descriptions** and **instructions for use**.
@snapend
@snap[content-10 text-center]
![](assets\img\pse-function-help.png)
@snapend

+++

### Expressions: Help Referencing Attributes
@snap[content]
@snap[content-10]
Referencing attributes can be tricky.
The help panel also gives us a way of **finding references** to specific attributes.
@ul[](false)
- Absolute paths
- Relative paths
@ulend
@snapend
@snap[content-10 text-center]
![](assets\img\pse-analysis-attribute-help.png)
@snapend
@snapend

+++

### Rollups
@snap[content]
@snap[content-10]
@ul[](false)
- Rollups perform calculations on a **variable number of child elements** such as:
    - Sum
    - Average
    - Min/Max
- References the same attribute for each child.
- Like expressions, outputs results to AF Attribute.
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-rollup.png)
@snapend

+++

### Event Frames

@snap[content]
@snap[content-10]
@ul[](false)
- Event Frames provide a way to **“bookmark”** interesting points of time (events).
- Are generated based on a defined set of **triggers**.
- Can collect attributes of interest using Event Frame Templates.
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-eventframes.png)
@snapend
@snapend

+++

### Event Frames - Triggering
@snap[content]
Event frames start when a **Start Trigger** is **true** for a set period of time and will end when an **End Trigger** is **true**.
@snapend
An End Trigger doesn't have to be defined...
<br>
@css[text-right](... the even frame will end when when the Start Trigger is **no longer true**.)
![](assets\img\pse-eventframe-trigger.png)

+++

### Event Frames - Templates

@snap[content]
@snap[content-10]
@ul[](false)
- Event Frame Templates specify:
    - What **attributes** should be associated with an Event Frame
    - What **naming scheme** Event Frames should follow when they are generated.
- Event Frames analyses cannot be defined without a template!
    - The template can be empty… it **just has to exist**!
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-eventframe-templates.png)
@snapend
@snapend

+++

### Viewing Recorded Event Frames
@snap[content]
@snap[content-10]
@ul[](false)
- Recorded Event Frames can be viewed from the “Event Frames” tab in PSE.
- Can perform searches to filter results.
@snapend
@snap[content-12]
![](assets\img\pse-eventframe-list.png)
@snapend
@snapend

+++

### SQC (Statistical Quality Control)
@snap[content]
@snap[content-10]
@ul[text-08](false)
- SQC defines allowable **deviances** from a desired **operating range** of an attribute.
- Deviances can be recorded to:
    - Event Frames
    - AF Attributes
@ulend
@snapend
@snapend
@snap[south]
![](assets\img\pse-sqc.png)
@snapend

+++

### Triggering Analyses
@snap[content]
@snap[content-10]
@ul[](false)
- Analyses can trigger based on two types of triggers:
    - **Periodic**: Runs at a set interval.
    - **Event-Triggered**: Runs when it detects a change in inputs.
        - Can select which inputs can act as a trigger.
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-analysis-triggering.png)
@snapend

+++

### Backfilling
@snap[content]
@snap[content-10]
@ul[](false)
- What happens if we make a change an analysis?
    - There will be an artificial **inflection point** in the data from the moment of change!
- We can have an analysis rewrite tag history / recreate Event Frames by **backfilling**.
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-analysis-backfilling.png)
@snapend
@snapend

+++

### Managing Analyses
@snap[content]
@snap[content-10]
@ul[](false)
- A list of all analyses in an AF database can be found in the Management tab.
- Can filter view based on search criteria.
- Can turn analyses on/off, backfill them.
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-managing-analyses.png)
@snapend
@snapend

+++

### Creating Output PI Points for Analysis Attributes
@snap[content]
@snap[content-10]
@ul[](false)
- PI AF can create referenced PI Points.
- Attribute’s data reference settings become PI Point’s configuration.
- Incredibly powerful when used with templates. Very often used to contain outputs from analyses.
- Triggered by<br>**“Create or Update PI Point”**
@ulend
@snapend
@snap[content-10]
![](assets\img\pse-analysis-create-pi-point.png)
@snapend
@snapend

+++

### Beyond AF Analytics
@snap[content]
@snap[content-10]
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
@snap[content-10]
When AF Analytics are not enough, we can read from and write back to the PI System through two different pathways:
@ul[](false)
- **PI Web API**: Provides read/write access to PI data over the web (http).
- **AFSDK**: Provides programmatic access to PI data and PI System configuration locally.
@ulend
While this can be a lot more to manage, it gives us the benefit of much more freedom!
@snapend
@snapend