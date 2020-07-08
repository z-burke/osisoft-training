@snap[west]
## Attributes and Their Data References
@snapend

+++

@snap[north-west]
### PI Asset Framework Data References
Each attribute points to **1** data reference. There are **6 types**:
@ul[text-09](false)
- Formula
- PI Point
- PI Point Array (not covered here)
- String Builder
- Table Reference
- URI
@ulend
@snapend
@snap[south-east span-45]
![IMAGE](assets/img/pse-data-references.png)
@snapend

+++

@snap[north-west]
### PI Point Data Reference
@ul[text-09 span-50](false)
- Provides direct access to **PI Tags in Data Archive**.
- Can set several different retrieval methods.
- **Most common data reference**. Most other data references build off of attributes of this reference type!
@ulend
@snapend
@snap[south-east span-45]
![](assets/img/pse-pi-point-data-reference.png)
@snapend

+++

### Configuring PI Point Data References
@snap[content]
@snap[flex-10]
@ul[](false)
- Can refer to:
    - PI Points directly
    - PI Points possessed by other attributes
- Source Units
- Value retrieval
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-pi-point-data-reference-config.png)
@snapend
@snapend

+++

### Configuring PI Point Data References
@snap[content flex-10]
@snap[flex-10]
Each value within a PI Point is recorded at a **discrete** time.
What happens if we query data in **between two recorded values**?
This is the purpose of **value retrieval methods**: a basic form of calculation!
@snapend
@snap[flex-10]
![height=400](assets/img/pse-pi-point-data-reference-config-value-retrieval.png)
@snapend
@snapend

+++

@snap[north-west]
### String Builder Data Reference
@ul[span-50](false)
- Generate a **string** based on other data within AF.
- Useful for **generating text** that may be a mixture of data from several different attributes.
- Can utilize substitution syntax.
@ulend
@snapend
@snap[east span-45]
![](assets/img/pse-string-builder-data-reference.png)
@snapend

+++

@snap[north-west]
### Table Data Reference
@ul[span-50](false)
- **SQL-style** queries on tables within AF.
- Useful for accessing static data or data that is coming from a SQL database.
- Can add data to tables by copying and pasting from Excel!
@ulend
@snapend
@snap[east span-45]
![](assets/img/pse-table-data-reference.png)
@snapend

+++

@snap[north-west]
### Formula Data Reference
@ul[span-50](false)
- Provides the ability to perform **basic calculations** that take data from other attributes as input.
- Note: the results are **not historiezed**!
@ulend
@snapend
@snap[east span-45]
![](assets/img/pse-formula-data-reference.png)
@snapend

+++

@snap[north-west]
### URI Data Reference
@ul[span-50](false)
- Provides a **dynamic URL**.
- Typically points to a PI Vision dashboard.
- Can be used in dashboards and PI Notifications.
@ulend
@snapend
@snap[east span-45]
![](assets/img/pse-uri-data-reference.png)
@snapend

