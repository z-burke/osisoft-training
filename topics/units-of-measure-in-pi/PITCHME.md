@snap[west]
## Units of Measure in PI
@snapend

+++

### Units of Measure on PI Points

@snap[content flex-10]
@snap[flex-10]
UOM's for PI Points are stored as the Point's **Eng Units** property.
@ul[text-11](false)
- Can be configured in PI SMT
- Stored as a simple string
- No restrictions on what's entered here
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/uom-pi-point.png)
@snapend
@snapend

+++

### Units of Measure on AF Attributes
@snap[content flex-10]
@snap[flex-10]
UOM's for AF Attributes are are stored as the Attribute's **Default UOM** property.
@ul[](false)
- Can be configured in System Explorer.
- Chosen from a predefined set.
- Can perform automatic UOM conversions.
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/af-attribute-uom.png)
@snapend
@snapend

+++

### Exercise: Setting Attribute UOM's
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-setting-attribute-uoms.gif)
@css[text-07](Changing UOM's doesn't change the value. There's no UOM associated with the PI Point, yet!)
@snapend
@snapend

+++

### Units of Measure in AF
@snap[content flex-10]
@snap[flex-10]
Define: canonical, reference, class
@ul[](false)

@ulend
@snapend
@snapend

+++

### Converting PI Point to Attribute UOM's
@snap[content flex-10]
@snap[flex-10]
Converting UOM's between Attributes and their PI Point requires setting a UOM within the data reference settings.
@ul[](false)
- This doesn't take into account the Engr Units of the PI Point, itself.
- Choices of UOM's are constrained to the same class of the Attribute.
- Once set, this will change the Attribute value. AF automatically performs the unit conversion! 
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-attribute-pi-point-uom.png)
@snapend
@snapend


+++

### Exercise: Converting PI Point to Attribute UOM's

@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pi-point-retrieval-uom-change.gif)
@css[text-07](Now changing the Attribute's UOM will change its value based on unit conversion.)
@snapend
@snapend

+++

### Converting UOM's Between Attributes

@snap[content flex-10]
@snap[flex-10]

@ul[](false)

@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-converting-attribute-uoms.png)
@snapend
@snapend

+++

### Exercise: Converting UOM's Between Attributes
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-converting-attribute-uoms.gif)
@css[text-07]()
@snapend
@snapend

+++

### The UOM AF Database
@snap[content flex-10]
@snap[flex-10]
AF UOM's in AF are kept in a single database
@ul[](false)
- Shared between AF Databases on the same server.
- Accessible through the **Unit of Measure** tab in System Explorer.
- Units within the same **class** can be converted between relative to a **canonical unit**.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pse-uoms.png)
@snapend
@snapend

+++

### Exercise: Exploring Configuration of a UOM
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-investigate-uoms.gif)
@css[text-07]()
@snapend
@snapend


+++



+++

+++

### Converting Between PI Point and Attribue UOM's
@snap[content flex-10]
@snap[flex-10 flex-center]
![height=450](assets/img/pi-point-retrieval-uom-change.gif)
@snapend
@snapend
@snap[content]
@snap[flex-10 text-center text-08]
PI Point Data References can automatically configure between PI Point and AF Attribute UOM's if configured correctly.
@snapend
@snapend

+++

### Converting Between AF Attribute UOM's
@snap[content flex-10]
@snap[flex-10 flex-center]
![height=450](assets/img/af-attribute-uom-conversion.gif)
@snapend
@snapend
@snap[content]
@snap[flex-10 text-center text-08]
AF automatically converts UOM's between Attributes for us.
@snapend
@snapend

