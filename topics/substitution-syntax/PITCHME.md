@snap[west]
## Substitution Syntax
@snapend

+++

### Substitution Syntax
@snap[content]
@snap[flex-10]
Elements inheriting from the same Template may have the same Attributes defined for them, but that doesn't mean we want them looking at the same exact data!
Substitution syntax allows for some flexibility here.
@ul[](false)
- Our assets may have the same attributes defined for them, but this doesn’t mean we want them looking at the exact same data!
- **Substitution syntax** allows for Attribute data references in the template to be specified as **variables**.
- Elements inheriting from this template will **resolve** these variables with respect to their individual **contexts**.
@ulend
@snapend
@snapend

+++

### Substitution Syntax
@snap[content flex-10]
@snap[flex-10 flex-center]
![height=400](assets/img/pse-substitution-syntax.png)
@snapend
@snapend

+++

### Substitution Syntax - Example Parameters
@snap[content flex-10]
@snap[flex-10 text-center text-09]
|   Parameter   |                         Description                        |
|:-------------:|:----------------------------------------------------------:|
|  %Attribute%  |     Name of the attribute containing the data reference    |
| %Description% | Description of the attribute containing the data reference |
|   %Element%   |        Name of the element containing the attribute        |
|    %Server%   |  Name of the default Data Archive (on the client machine)  |
|   %Template%  |   Name of the template the element directly inherits from  |
@snapend
@snapend

+++

### Substitution Syntax - Example Modifiers
@snap[content]
@snap[flex-10 text-center text-09]
| Modifier |                       Definition                       |             Examples            |
|:--------:|:------------------------------------------------------:|:-------------------------------:|
|  %param% |     Consider expression as a substitution parameter    |      %Element% %Attribute%      |
|     .    |                  Navigate a level down                 |     %@.\Element\|Attribute%     |
|    ..    |                   Navigate a level up                  | %..\..\Element% %..\|Attribute% |
|     /    |                  References an element                 |           %..\Element%          |
|    /|    |                 References an attribute                |  %..\|Attribute% %@\|Attribute% |
|     @    | References the value of the object instead of its name |       %@....\|Attribute%       |
@snapend
@snapend
@snap[content]
@snap[flex-10 text-08]
*Italicized text should be replaced with appropriate text (element or attribute name)*
@snapend
@snapend

+++

### Exercise: Use Substitution Syntax to Reference Another Attribute's Data
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-substitution-syntax-pi-point-data-reference.gif)
@css[text-07]()
@snapend
@snapend

+++

### Exercise: Replicate More Attributes With Substitution Syntax
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-replicate-attributes-with-substitution.gif)
@css[text-07]()
@snapend
@snapend

+++

### Where Substitution Syntax Can Be Used

@snap[content]
@snap[flex-10 text-12]
@ul[](false)
- AF Attribute Data References
    - AF Templates
    - AF Tables
    - String Builder
- AF EventFrames
@ulend
@snapend
@snapend

@snap[south text-center span-100]
Tip: If you're having trouble, it's often easiest to test using<br>String Builder.
@snapend