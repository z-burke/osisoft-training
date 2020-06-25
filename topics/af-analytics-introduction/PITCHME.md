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
@snap[content-9]
@ul[](false)
- Expressions
- Rollups
- Event Frame Generation
- SQC
@ulend
@snapend
@snap[content-10 flex-center-y]
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
@snapend