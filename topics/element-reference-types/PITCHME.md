@snap[west]
## Reference Types Between Elements in AF
@snapend

+++

### Element Reference Types
@snap[content]
@snap[flex-10]
Reference types allow for elements to exist in **more than one place in the hierarchy**:
@ul[](false)
- **Parent-child**: The same element can exist in multiple places. Will only be deleted when the last “strong” reference to it is deleted.
- **Composition**: Binds the child to the parent, so if the parent is deleted the child is deleted as well (including all other references to it).
- **Weak**: Like a parent-child reference, but it cannot stand on its own. If stronger references are deleted, this referenced instance will be deleted as well.
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-element-references.png)
@snapend
@snapend

+++

### Element Reference Types
@snap[content]
@snap[flex-10]
Reference types allow for elements to exist in **more than one place in the hierarchy**:
@ul[](false)
- A popular strategy is to use a combination of Parent-Child and Weak references.
    - **Parent-child** references are used where element is defined in hierarchy based on physical location (area, process, …).
    - **Weak** references are then build from these references to create equipment lists for SME.
- **Parent-child** is the **default** reference type in AF.
@ulend
@snapend
@snapend