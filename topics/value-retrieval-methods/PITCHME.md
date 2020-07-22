@snap[west]
## AF PI Point Value Retrieval Methods
@snapend

+++

### Value Retrieval Methods
@snap[content flex-10]
@snap[flex-10]
Every value recorded to a PI Point has both a **value** and a **timestamp**.
**Value retrieval methods** help us with two things:
@ol[](false)
1. **Time Retrieval Methods:** Give us a way to change what happens when AF queries a PI Point at a time **between** recorded values.
1. **Range Retrieval Methods:** Allow AF to perform simple calculations on recorded PI Point values over a **time range**.
@olend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-value-retrieval-attribute.png)
@snapend
@snapend

+++

### Time Retrieval Methods
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
@table[table-header table-tsv text-08](assets/data/time-retrieval-options.tsv)
@css[text-07](There are other methods, but these are only used when combined with **range retrieval methods**.)
@snapend
@snapend

+++

### Exercise: Attributes with Time Retrieval Methods
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-value-retrieval-attributes-time.gif)
@css[text-07]()
@snapend
@snapend

+++

### Range Retrieval Methods
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
@table[table-header table-tsv text-07](assets/data/range-retrieval-options.tsv)
@snapend
@snapend

+++

### Time Retrieval Methods for Range Retrievals
@snap[content]
If using a Range Retrieval method, we **must** use one of the Time Retrieval methods below.
@snapend
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
@table[table-header table-tsv text-08](assets/data/time-retrieval-options-calculations.tsv)
@snapend
@snapend

+++

### Exercise: Daily Number Pump Starts/Stops 
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-value-retrieval-event-count.gif)
@css[text-07]()
@snapend
@snapend

+++

### Limitation: Triggering Value Retrieval Methods
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Notice that the number of daily pump start/stops **doesn't update every time** the pump turns on or off.
- Instead, the count is updated at the current time and then at the **relative time** specified in the value retrieval settings.
- For this reason, value retrieval methods are often best used for data that **doesn't need to be trended**.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-value-retrieval-trigger.png)
@snapend
@snapend


+++

### Exercise: Average Hourly Bearing Temperature
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-value-retrieval-average.gif)
@css[text-07]()
@snapend
@snapend

+++

### Limitation: Lack of Context Awareness
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- There is a problem in our flow average. It includes time periods when the pump is off!
- Value retrieval methods **cannot account for conditionals** on their own. If this is problematic, we may need additional tools!
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-value-retrieval-conditional.png)
@snapend
@snapend
