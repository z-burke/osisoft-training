@snap[west]
## AF Analytics: Event Frames
@snapend

+++

### How EventFrame Analyses are Structured
@snap[content]
@snap[flex-10]
Analysis of an **EventFrame** type are unique. They:
@ol[](false)
1. Are recorded in AF (rather than Data Archive).
2. Can be associated with data from AF Attributes via **EventFrame Templates**.
3. Are created when a set of **triggering conditions** is satisfied.
@olend
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-eventframes.png)
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