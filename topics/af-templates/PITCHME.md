@snap[west]
## AF Element Templates
@snapend

+++

### AF Templates
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Many assets are **instances of the same type** of equipment.
    - We want to see the same attributes for each one of them…
    - … but **don’t want to individually define attributes** for each one.
- AF Templates allow us to **define all these attributes of the same type once**, then attach these attributes to each of these elements by associating them with a common template.
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-element-templates.png)
@snapend
@snapend

+++

### Defining AF Templates
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- AF Templates are defined in the **“Library”** tab of PSE.
- Each template defines:
    - Attributes
    - Analyses
    - Notification Rule Templates
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-element-template-library.png)
@snapend
@snapend

+++

### Associating an AF Element with a Template
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- Pre-existing elements can be associated with a template after they’ve already been created.
- Careful! This will **delete the attributes already defined** for this element!
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-changing-element-template.png)
@snapend
@snapend

+++

### Exercise: Creating an AF Element Template
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-create-element-template.gif)
@css[text-07]()
@snapend
@snapend

+++

### Exercise: Associating an Element with a Template
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-associate-element-with-template.gif)
@css[text-07]()
@snapend
@snapend

+++

### Converting an Element to a Template
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- You can also define templates **based on elements that have already been created**.
- (Notice this can’t be done for Elements that are already associated with a template.)
@ulend
@snapend
@snap[flex-14 flex-center]
![](assets/img/pse-convert-element-to-template.png)
@snapend
@snapend

+++

### Exercise: Converting an Element to a Template
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-convert-element-to-template.gif)
@css[text-07]()
@snapend
@snapend

+++

### What Templates Control About Attributes
@snap[content flex-10]
@snap[flex-14]
As soon as you apply a Template to an Element, you **cannot add new Attributes**.
However, there are certain configuration items of template-defined Attributes you **can edit** at the Element level.   
@ul[](false)
- **Description**
- **Excluded** property<br>(used to mark Attributes defined by Template that don't exist for the Element)
- **Value** (if not read from Data Reference)
- **Data Reference**
@ulend
@snapend
@snap[flex-10 flex-center]
![height=450](assets/img/pse-template-defined-attribute.png)
@snapend
@snapend

+++

### Exercise: Setting Data Reference for a Template-Defined Attribute
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-setting-attribute-template-data-reference.gif)
@css[text-07]()
@snapend
@snapend

+++

### Resetting Attributes to Templates
@snap[content flex-10]
@snap[flex-14]
Some configuration items for Attributes (see previous slide) can be defined at the Template or Element level.
@ul[](false)
- The Element always **overrides** what's specified as the default in the Template.
- Any deviations from the template can be reversed using the **reset to Template** command. 
@ulend
Be careful, this can cause data references set at the Element level to **disappear**!
@css[text-08](*Consider keeping a backup using a tool like PI Builder.*)
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-reset-to-template.png)
@snapend
@snapend

+++

### Exercise: Resetting Attribute to Template
@snap[content flex-10 flex-center text-center]
@snap[flex-10]
![height=450](assets/img/pse-reset-to-template.gif)
@css[text-07]()
@snapend
@snapend

+++
+++
+++

### Derived Templates
@snap[content flex-10]
@snap[flex-10]
@ul[](false)
- But what about cases where there are **subtypes** of different asset types (i.e. different types of compressors?)
- For these cases, we create multiple templates that **inherit from one another**.
- Templates are typically organized so more **specific** types of an asset inherit from more **general** types.
@ulend
@snapend
@snap[flex-10 flex-center]
![height=450](assets/img/pse-derived-templates.png)
@snapend
@snapend

+++

### Viewing Templates in Hierarchy Based on Inheritance
@snap[content flex-10]
@snap[flex-10 flex-center]
![](assets/img/pse-viewing-template-inheritance.png)
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


### NEVER Allow Extensions to Templates

+++