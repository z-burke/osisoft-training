MAIN

---?include=topics/pi-vision/PITCHME.md

---?include=topics/pi-datalink/PITCHME.md

---?include=topics/pi-builder/PITCHME.md



ANALYTICS: EXPRESSION


+++

### Triggering Analyses
@snap[content]
@snap[flex-10]
Triggering refers to how often an analysis calculates new data.
This is a tradeoff between frequency of data updates and load on the Analysis service.
There are two forms of triggering:
- Event-Triggered: Calculates every time input Attribute(s) receive new data.
- Periodic: Calculates at a set frequency (i.e. once every 5 minutes).
@snapend
@snap[flex-10 text-center]
![](assets/img/.png)
@snapend
@snapend

+++

### Exercise: Observing Effects of Different Triggers
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend

+++



### Mapping Analyses to Attributes
@snap[content]
@snap[flex-10]

For example, this can be combined with Digital States to only calculate expressions when certain prerequisites are met.
@snapend
@snap[flex-10 text-center]
![](assets/img/.png)
@snapend
@snapend

+++

### Exercise: Mapping Analyses to Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend

+++

### Exercise: Setting Parameters for Attribute Creation
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07](Note: the security settings required by your Analysis service are likely different.)
@snapend
@snapend

+++

### Exercise: Creating a PI Point from an Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend

+++

### Exercise: Backfilling PI Points (via Element)
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend

+++

### Exercise: Backfilling PI Points (via Management Tab)
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend



+++



ANALYTICS: ROLLUPS

+++



### Exercise: Creating a Rollup Analysis
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/.gif)
@css[text-07]()
@snapend
@snapend

+++



ANALYTICS: EVENT FRAMES


