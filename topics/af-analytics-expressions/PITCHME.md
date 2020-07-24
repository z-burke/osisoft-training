@snap[west]
## AF Analytics: Expressions
@snapend

+++

### How Expression Analyses are Structured
@snap[content]
@snap[flex-10]
Each Analysis of an **expression** type:
@ol[](false)
1. Consists of several expression that each output to a **variable**
1. Each variable can output its value to an **AF Attribute**
1. If these AF Attributes are PI Point Data References, resulting values will be written to the PI tag (**historized**)
@olend
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-expressions.png)
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

### Expressions: Using Conditionals
@snap[content]
@snap[flex-10]
@css[green-emphasis](IF - THEN) statements can be used to conditionally evaluate expressions.

```excel zoom-12
IF ('Pump Status' = "ON") AND
  (HasChanged('Pump Status', StartTime) = False)
  // Calculate average if pump has been on since start time.
  THEN TagAvg('Discharge Flow Rate', StartTime, '*')
  ELSE DigState("No Data")
```
<br>
For example, this can be combined with Digital States to only calculate expressions when certain prerequisites are met.
@snapend
@snapend

+++

### Exercise: Conditional in an Expression
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-analysis-expression-conditional.gif)
@css[text-07](Shift+Enter starts a new line.)
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
