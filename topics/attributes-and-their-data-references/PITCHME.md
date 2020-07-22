@snap[west]
## Attributes and Their Data References
@snapend

+++

### PI Asset Framework Data References
@snap[content flex-10]
@snap[flex-10]
Each attribute points to **1** data reference. There are **6 types**:
@ul[](false)
- Formula
- PI Point
- PI Point Array (not covered here)
- String Builder
- Table Reference
- URI
@ulend
@snapend
@snap[flex-10 flex-center]
![height=350](assets/img/pse-data-references.png)
@snapend
@snapend

+++

### Configuring Data References
@snap[content flex-10]
@snap[flex-14]
Every **AF Attribute** stores the information it needs to look up its data reference as a **configuration string**.
@ul[](false)
- We can edit these configuration strings directly if we'd like  **(1)**.
- However, it's much easier to do so through the **Settings...** menu **(2)**.
@ulend
**NOTE:** The configuration string (and the "Settings..." menu) changes for each Data Reference type!)
@snapend
@snap[flex-10 flex-center]
![height=500](assets/img/pse-data-reference-settings.png)
@snapend
@snapend

+++

### PI Point Data Reference
@snap[content flex-10]
@snap[flex-10]
Provides direct access to **PI Tags in Data Archive**.
@ul[](false)
- Can also reference PI Points **indirectly** by referencing other Attributes.
- Retrieval methods can be set to perform **basic calculations**.
@ulend
**Most common data reference**. Most other data references build off of attributes of this reference type!
@snapend
@snap[flex-10 flex-center]
![height=450](assets/img/pse-pi-point-data-reference.png)
@snapend
@snapend

+++

### Exercise: PI Point Data Reference Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-pi-point-data-reference.gif)
@css[text-08](Use the name of the tag we created earlier!)
@snapend
@snapend

+++


### String Builder Data Reference
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Generate a **string** based on other data within AF.
- Useful for **generating text** that may be a mixture of data from several different attributes.
- Can utilize substitution syntax.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pse-string-builder-data-reference.png)
@snapend
@snapend

+++

### Exercise: String Builder Data Reference Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-string-builder-data-reference.gif)
@snapend
@snapend

+++

### Table Data Reference
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- **SQL-style** queries on tables within AF.
- Useful for accessing static data or data that is coming from a SQL database.
- Can add data to tables by copying and pasting from Excel!
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pse-table-data-reference.png)
@snapend
@snapend

+++

### Exercise: Creating an AF Table
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-af-table.gif)
@snapend
@snapend

+++

### Exercise: Table Lookup Data Reference Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-table-lookup-data-reference.gif)
@snapend
@snapend

+++

### Formula Data Reference
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Provides the ability to perform **basic calculations** that take data from other attributes as input.
- Note: the results are **not historiezed**!
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pse-formula-data-reference.png)
@snapend
@snapend

+++

### Exercise: Formula Data Reference Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-formula-data-reference.gif)
@snapend
@snapend

+++

### URI Data Reference
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Provides a **dynamic URL**.
- Typically points to a PI Vision dashboard.
- Can be used in dashboards and PI Notifications.
@ulend
@snapend
@snap[flex-12 flex-center]
![](assets/img/pse-uri-data-reference.png)
@snapend
@snapend

+++

### Exercise: URI Data Reference Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-uri-data-reference.gif)
@snapend
@snapend
