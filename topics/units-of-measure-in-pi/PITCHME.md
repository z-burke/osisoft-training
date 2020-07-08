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
@ul[text-11](false)
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

+++

### Configuring UOM's in AF
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

