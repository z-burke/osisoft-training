@snap[west]
## Calculations in PI
@snapend

+++

### Two Types of Data
@snap[content]
@snap[flex-10]
**Operational**
@ul[text-11](false)
- Directly measurable quantities
- Physical, "no undo"
- i.e. Sensor readings
    - Flow rate
    - Temperature
@ulend
@snapend
@snap[flex-10 text-11]
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
@snap[content flex-center text-center]
@snap[flex-10]
Calculations in PI generally exist to generate @css[green-emphasis](strategic) data.
@snapend
@snapend

+++
### Types of Calculations in PI
@snap[content]
@snap[flex-10]
@ul[text-11](false)
- **Tag-based**
    - PI Performance Equations (not recommended)
    - PI Totalizers (not recommended)
- **Asset Analytics**
    - Value retrieval methods
    - Formula data references
    - AF Analytics
- **Programmatic Analytics**
    - Advanced Calculation Engine (not recommended)
    - PI AF SDK
    - PI Web API
@snapend
@snapend

+++

### Value Retrieval Methods
@snap[content flex-10]
@snap[flex-10]
Grants control over how values are read from PI Points.
@ul[](false)
- Can be configured from the PI Point Data Reference settings menu.
- Can select whether values are interpolated.
- Can also provide some basic averaging or totalizing.
- Only reads from one PI Point at a time.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/value-retrieval-methods.png)
@snapend
@snapend

+++

### Formula Data References
@snap[content flex-10]
@snap[flex-10]
Create simple analytics from the Formula Data Reference settings menu.
@ul[](false)
- Provides basic functions.
- Can take inputs from multiple attributes.
- Not historized.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/formula-data-reference.png)
@snapend
@snapend

+++

### AF Analytics
@snap[content flex-10]
@snap[flex-10]
Real-time calculation engine bundled with PI AF.
@ul[](false)
- Can configure calculations from within System Explorer.
- Utilitzes and Excel formula-like syntax.
- Can historize data to PI Points.
@snapend
@snap[flex-12 flex-center]
![](assets/img/af-analytics.png)
@snapend
@snapend

+++

### PI AF SDK & PI Web API
@snap[content flex-10]
@snap[flex-10]
Programmatic access to the PI System.
@ul[](false)
- **PI AF SDK**: local via a .NET language (C#, PowerShell, etc.)
- **PI Web API**: over http via any language capable of restful API calls.
- Provides most freedom.
- Most complex option.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pi-af-sdk-and-pi-web-api.png)
@snapend
@snapend
