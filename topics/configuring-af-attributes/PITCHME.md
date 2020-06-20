## Configuring AF Attributes

+++

@snap[north-west]
### Configuring AF Attributes
@snap[span-50]
Attributes carry **metadata** with them.
@snapend
@ul[span-50](false)
- Can provide more **meaningful information** about the attribute.
- Serve as **instructions** for how AF should treat the attribute.
@ulend
@snapend
@snap[east span-45]
![](assets\img\pse-attribute-configuration.png)
@snapend

+++

@snap[north-west]
### Configuring PI Point Data References
@ul[span-50](false)
- Can refer to:
    - PI Points directly
    - PI Points possessed by other attributes
- Source Units
- Value retrieval
@ulend
@snapend
@snap[east span-45]
![](assets\img\pse-pi-point-data-reference-config.png)
@snapend

+++

@snap[north-west]
### Configuring PI Point Data References
@snap[span-50]
Each value within a PI Point is recorded at a **discrete** time.
What happens if we query data in **between two recorded values**?
This is the purpose of **value retrieval methods**: a basic form of calculation!
@snapend
@snapend
@snap[east span-45]
![height=400](assets\img\pse-pi-point-data-reference-config-value-retrieval.png)
@snapend

+++

@snap[north-west]
### Enumeration Sets
@snap[span-50]
Constrains data references to a **defined set of values** 
Example: ON or OFF
Looks like text, but really stored as a number.
@snapend
@snapend
@snap[east span-45]
![height=400](assets\img\pse-enumeration-sets.png)
@snapend