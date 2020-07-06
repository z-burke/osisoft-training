@snap[west]
## Asset Framework Templates
@snapend

+++

### AF Templates
@snap[content]
@snap[flex-10]
@ul[](false)
- Many assets are **instances of the same type** of equipment.
    - We want to see the same attributes for each one of them…
    - … but **don’t want to individually define attributes** for each one.
- AF Templates allow us to **define all these attributes of the same type once**, then attach these attributes to each of these elements by associating them with a common template.
@ulend
@snapend
@snap[flex-10]
![](assets\img\pse-element-templates.png)
@snapend
@snapend

+++

### Defining AF Templates
@snap[content]
@snap[flex-10]
@ul[](false)
- AF Templates are defined in the **“Library”** tab of PSE.
- Each template defines:
    - Attributes
    - Analyses
    - Notification Rule Templates
@ulend
@snapend
@snap[flex-10]
![](assets\img\pse-element-template-library.png)
@snapend
@snapend

+++

### Associating an AF Element with a Template
@snap[content]
@snap[flex-10]
@ul[](false)
- Pre-existing elements can be associated with a template after they’ve already been created.
- Careful! This will **delete the attributes already defined** for this element!
@ulend
@snapend
@snap[flex-10]
![](assets\img\pse-changing-element-template.png)
@snapend
@snapend

+++

### Creating a New Template from an Existing Element
@snap[content]
@snap[flex-10]
@ul[](false)
- You can also define templates **based on elements that have already been created**.
- (Notice this can’t be done for Elements that are already associated with a template.)
@ulend
@snapend
@snap[flex-10]
![](assets\img\pse-convert-element-to-template.png)
@snapend
@snapend

+++

### Substitution Syntax
@snap[content]
@snap[flex-10]
@ul[](false)
- Our assets may have the same attributes defined for them, but this doesn’t mean we want them looking at the exact same data!
- **Substitution syntax** allows for Attribute data references in the template to be specified as **variables**.
- Elements inheriting from this template will **resolve** these variables with respect to their individual **contexts**.
@ulend
@snapend
@snapend

+++

### Substitution Syntax
@snap[content]
@snap[flex-10]
![](assets\img\pse-substitution-syntax.png)
@snapend
@snapend

+++

### Substitution Syntax - Example Parameters
@snap[content]
@snap[flex-10]
|   Parameter   |                         Description                        |
|:-------------:|:----------------------------------------------------------:|
|  %Attribute%  |     Name of the attribute containing the data reference    |
| %Description% | Description of the attribute containing the data reference |
|   %Element%   |        Name of the element containing the attribute        |
|    %Server%   |  Name of the default Data Archive (on the client machine)  |
|   %Template   |   Name of the template the element directly inherits from  |
@snapend
@snapend

+++

### Substitution Syntax - Example Modifiers
@snap[content]
@snap[flex-10]
| Modifier |                       Definition                       |             Examples            |
|:--------:|:------------------------------------------------------:|:-------------------------------:|
|  %param% |     Consider expression as a substitution parameter    |      %Element% %Attribute%      |
|     .    |                  Navigate a level down                 |     %@.\Element\|Attribute%     |
|    ..    |                   Navigate a level up                  | %..\..\Element% %..\|Attribute% |
|     \    |                  References an element                 |           %..\Element%          |
|    \|    |                 References an attribute                |  %..\|Attribute% %@\|Attribute% |
|     @    | References the value of the object instead of its name |       %@..\..\|Attribute%       |
*Italicized text should be replaced with appropriate text (element or attribute name)*
@snapend
@snapend

+++

### Creating a New Template from an Existing Element
@snap[content]
@snap[flex-10]
@ul[](false)
- But what about cases where there are **subtypes** of different asset types (i.e. different types of compressors?)
- For these cases, we create multiple templates that **inherit from one another**.
- Templates are typically organized so more **specific** types of an asset inherit from more **general** types.
@ulend
@snapend
@snap[flex-10]
![](assets\img\pse-derived-templates.png)
@snapend
@snapend

+++

### Viewing Templates in Hierarchy Based on Inheritance
@snap[content]
@snap[flex-10]
![](assets\img\pse-viewing-template-inheritance.png)
@snapend
@snapend

+++

### Template Inheritance Patterns
@snap[content]
@snap[flex-10]
**Pattern #1: Adding Attributes**
@ul[](false)
- Attributes defined in a child attribute (but not in the parent) will be **added** to an element associated with it.
- **No impact** on the parent’s attributes.
@ulend
@snapend
@snap[flex-10]
**Pattern #2: Overwriting Attributes**
@ul[](false)
- If an attribute is **defined in both** the parent and child templates, the child template will **overwrite** the parent template.
- Based on attribute name.
@ulend
@snapend
@snapend