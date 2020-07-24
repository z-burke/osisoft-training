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

### How Analyses are Structured
@snap[content]
@snap[flex-10]
Each Analysis (regardless of type):
@ol[](false)
1. Is **started/stopped** as a unit
1. Collectively runs at a configurable **frequency**
1. Can be **backfilled** (to recalculate over past time spans)
@olend
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-expression.png)
@snapend
@snapend

+++

### Analyses and Templates
@snap[content]
@ul[text-11](false)
- Consider leaving Analyses off until explicitly enabled (alllows for testing)
- It's technically possible to create analyses at the Element level (instead of the Template).
    - However, this is not recommended.
    - If Elements of the same Template have the same Attributes, why not calculate the same thing?
@ulend
@snapend

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