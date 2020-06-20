## AF Analytics - Introduction

+++

@snap[north text-left]
### Two Types of Data
@snapend
@snap[weast span-50]
**Operational**
@ul[](false)
- Directly measurable quantities
- Physical, "no undo"
- i.e. Sensor readings
    - Flow rate
    - Temperature
@ulend
@snapend
@snap[east span-50 text-left]
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

+++

@snap[north-west]
### Units of Measure in PI
@ul[span-50](false)
- All kept in a **single database**.
- UOM's each inherit from one **canonical type**.
- Asset Framework **takes care of unit conversions for us**.
    - The UOM label for PI Points in Data Archive doesn't affect how AF processes data.
    - UOM of PI points is set by the PI Point data reference configuration.
@ulend
@snapend
@snap[east span-45]
![](assets\img\pse-uoms.png)
@snapend