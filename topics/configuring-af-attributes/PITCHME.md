@snap[west]
## Configuring AF Attributes
@snapend

+++

### Configuring AF Attributes
@snap[content flex-10]
@snap[flex-10]
In addition to their data references, AF Attributes carry other **metadata** with them.
@ul[](false)
- Can provide more **meaningful information** about the attribute.
- Serve as **instructions** for how AF should treat the attribute.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-attribute-configuration.png)
@snapend
@snapend

+++

### Attribute Configuration Fields
@snap[content flex-10]
@snap[flex-20]
@ul[text-08](false)
- **Name:** The unique label for the Attribute.
- **Description:** Provides a more detailed description of the object.
- **Properties:** Miscellanious set of fields that determine how AF should treat the Attribute.
- **Categories:** Labels that can be used for querying and/or reporting purposes.
- **Default UOM:** Defines the default unit of measure for the Attribute's value.
- **Value Type:** The type of data the Attribute's value contains.
- **Value:** The value stored by the Attribute or obtained by the Attribute's data reference.
- **Display Digits:** Controls the format of numeric values on displays and in reports.
- **Data Reference:** From where an Attribute should retrieve data and how.
- **Settings:** Sets the configuration string for the Attribute's Data Reference.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-attribute-configuration-fields.png)
@snapend
@snapend

+++

### Attribute Properties
@snap[content flex-10]
@snap[flex-14]
@ul[text-09](false)
- **Configuration Item:** Whether the Attribute requires a check out and check out in order to change its value.
- **Hidden:** If hidden, the Attribute is not returned in searches and will not be visible in some applications, but it can still return a value.
- **Manual Data Entry:** Whether the Attribute is marked for manual data entry.
- **Location:** Can configure the Attribute to act as a Latitude, Longitude, or Altitude for its parent Element.
- **Health:** Can use the Attribute to act as a Health Score or Health Status for its parent Element.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-attribute-properties.png)
@snapend
@snapend

+++

### Exercise: Creating a Configuration Item
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-configuration-item.gif)
@css[text-08](Note how changing the Attribute value puts a check on the Element.)
@snapend
@snapend

+++

### Attribute Categories
Configuration item
@snap[content flex-10]
@snap[flex-10]
In addition to their data references, AF Attributes carry other **metadata** with them.
@ul[](false)
- Can provide more **meaningful information** about the attribute.
- Serve as **instructions** for how AF should treat the attribute.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-attribute-configuration.png)
@snapend
@snapend

+++

### Exercise: Categorizing Attributes
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-categorize-attributes.gif)
@snapend
@snapend

+++

### Value Types
@snap[content flex-10]
@snap[flex-10]
Constrains data references to a **defined set of values** 
Example: ON or OFF
Looks like text, but really stored as a number.
If in doubt, for numerical values use the type **double**
"Array" data types are used much less frequently.
@snapend
@snap[flex-10 flex-center]
![height=500](assets/img/pse-attribute-value-types.png)
@snapend
@snapend

+++

### Exercise: Boolean Value Type Attribute

@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-boolean-value-type.gif)
@snapend
@snapend

+++

### Enumeration Sets

@snap[content flex-10]
@snap[flex-10]
Constrains data references to a **defined set of values** 
Example: ON or OFF
Looks like text, but really stored as a number.
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-enumeration-sets.png)
@snapend
@snapend

+++

### Exercise: Creating an Enumeration Set

@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-enumeration-set.gif)
@snapend
@snapend

+++

### Exercise: Enumeration Set Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-enumeration-value-type.gif)
@snapend
@snapend
