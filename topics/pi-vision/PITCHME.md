@snap[west]
## PI Vision
@snapend

+++

### PI Vision
@snap[content]
@snap[flex-10]
OSIsoft's web-based dashboarding tool for visualizing PI System data.
@ul[](false)
- Easily build displays using PI System data
- View real-time or historical data
- Reuse displays for assets of the same type
- View ProcessBook displays
@ulend
@snapend
@snap[flex-10 flex-center]
![]()
@snapend
@snapend

+++

### PI Vision vs. PI ProcessBook
@snap[content]
**PI Vision is the sucessor to PI ProcessBook**
@snapend
@snap[content]
@snap[flex-10]
PI Vision
@ul[](false)
- Web hosted
@ulend
@snapend
@snap[flex-10]
PI ProcessBook
@ul[](false)
- Desktop application
@ulend
@snapend
@snapend

+++

### Accessing PI Vision
@snap[content]
@snap[flex-10]
@ol[](false)
1. Use a modern web browser!
    - Chrome, Edge, FireFox
    - NOT Internet Explorer!!!
1. Navigate to the PI Vision URL
1. Provide username and password (if required)
@olend
@snapend
@snap[flex-10]
![](assets/img/vision-url.png)
![](assets/img/vision-login.png)
@snapend
@snapend

+++

### PI Vision Home Page
@snap[content]
@snap[flex-10]
@ol[](false)
1. Search box
1. Predefined groups
1. Display folders
1. New display button
1. Display
1. Display title
1. Display owner
1. Shared display icon
1. Settings
1. Favorite
@olend
@snapend
@snap[flex-20]
![](assets/img/vision-home-page.png)
@snapend
@snapend
@snap[content]
@snap[flex-10 text-09 text-center]
Let's create a display of our own. Click **New Display** to get started.
@snapend
@snapend

+++

### Display Workspace

@snap[content flex-10]
@snap[flex-10]
@ol[](false)
1. Symbol gallery
1. Assets Pane
1. Attributes pane
1. Editing Toolbar
1. Save button
1. Display area
1. Fit all and zoom
1. Timebar control 
@olend
@snapend
@snap[flex-20]
![](assets/img/vision-display-workspace.png)
@snapend
@snapend

+++

### PI Vision Symbols

@snap[content]
@snap[flex-10]
PI Vision illustrates process data in the form of **symbols**.
@snapend
@snapend
@snap[content]
@snap[flex-10 text-center]
![height=450](assets/img/vision-symbols.png)
@snapend
@snapend

+++

### Accessing PI Data

@snap[content flex-10]
@snap[flex-10]
PI data from 1 of 2 sources can be used in displays:
@ol[](false)
1. **PI Points** in a PI Data Archive
1. **AF Attributes** in PI Asset Framework
@olend
@css[text-08](*Note: AF Attributes often receive data from PI Points, themselves!*)
@snapend
@snap[flex-10]
![](assets/img/vision-data-sources.png)
@snapend
@snapend

+++

### AF Hierarchies in PI Vision

@snap[content flex-10]
@snap[flex-10]
If an **AF Database** is selected as a data source, we can browse the hierarchy and select Attributes to use in our display.
@ul[](false)
- The top pane shows **AF Elements**
- The bottom pane shows **AF Attributes** belonging to the selected element.
@ulend
@snapend
@snap[flex-10 flex-center]
![height=500](assets/img/vision-af-hierarchy.png)
@snapend
@snapend

+++

### Exercise: Creating a Gauge Symbol

@snap[content text-center]
@snap[flex-10]
![height=500](assets/img/vision-create-gauge.gif)
@snapend
@snapend

+++

### Formatting Symbols

@snap[content flex-10]
@snap[flex-10]
Right-click the symbol and select **Format Gauge...** to change its appearance.
@ul[](false)
- Colors
- Labels
- Numbers and Scales
@ulend
You can also resize symbols by clicking and dragging the corners.
@snapend
@snap[flex-10 flex-center]
![](assets/img/vision-format-gauge.png)
@snapend
@snapend
@snap[content text-center text-08]
@snap[flex-10]
*Note: Different gauges have different formatting options.*
@snapend
@snapend

+++

### Exercise: Formatting a Gauge

@snap[content text-center]
@snap[flex-10]
![height=500](assets/img/vision-format-gauge.gif)
@snapend
@snapend

+++

### Exercise: Creating a Table

@snap[content text-center]
@snap[flex-10 text-08]
![height=450](assets/img/vision-create-table.gif)
Hold *CTRL* to select multiple Attributes.
Notice we can add more Attributes by dragging and dropping.
@snapend
@snapend

+++

### Converting a Symbol

@snap[content flex-10]
@snap[flex-10]
Once a symbol has been created, it can be converted to a different one with the **same data** by right-clicking and selecting **Switch Symbol to...**
<br>
Keep in mind that not all symbols are interchangeable.
@snapend
@snap[flex-10 flex-center]
![](assets/img/vision-convert-symbol.png)
@snapend
@snapend

+++

### Exercise: Converting a Table to a Trend

@snap[content text-center]
@snap[flex-10 text-08]
![height=500](assets/img/vision-convert-symbol.gif)
Notice we can remove an Attribute from the symbol, too.
@snapend
@snapend

+++

### Saving a Display

@snap[content flex-10]
@snap[flex-10]
When we first changed the dashboard, two buttons became available to us that weren't earlier.
@ol[](false)
1. **Design mode button**: Switches the display between read-only and editing mode.
1. **Save button**: Saves the display.
@olend
Saving the display will make it available from the home page.
@snapend
@snap[flex-10 flex-center]
![](assets/img/vision-save-dashboard-buttons.png)
@snapend
@snapend

+++

### Exercise: Saving a Display

@snap[content text-center]
@snap[flex-10 text-08]
![height=500](assets/img/vision-save-display.gif)
@snapend
@snapend

+++

### Display Ownership

@snap[content flex-10]
@snap[flex-10]
There are two settings that determine who can view/edit displays:
@ul[](false)
1. **Display Owner**: Who has the ability to save changes to the display
1. **Share with**: Who has the ability to view wthe display
@ulend
By default, any displays we create are only visible to us.
@snapend
@snap[flex-10 flex-center]
![](assets/img/vision-display-ownership.png)
@snapend
@snapend

+++

### Exercise: Sharing Vision Displays

@snap[content text-center]
@snap[flex-10 text-08]
![height=500](assets/img/vision-share-display.gif)
@snapend
@snapend

+++

### Zooming and Fit All

@snap[content flex-10]
@snap[flex-10]
Three buttons allow for zooming in an out on a display:
@ol[](false)
1. **Zoom In**
1. **Zoom Out**
1. **Fit All**: Zooms in to fit all symbols in the display view
@olend
We can also zoom in and out by holding *CTRL* and using the scroll wheel.
@snapend
@snap[flex-16 flex-center]
![](assets/img/vision-zoom.png)
@snapend
@snapend

+++

### The Timebar

+++

### Exercise: Exploring Historical Data

+++

### Adding Images

+++

### Exercise: Adding Images

+++

### Adding Shapes

+++

### Exerice: Adding Shapes

+++

### Adding Text

+++

### Exercise: Adding Text

+++

### Exercise: Adding Text from Attribute

Useful for Asset specific text (name, manufacturer, etc.)

+++

### Multistate

+++

### Exercise: Adding Multistate

+++

### Context Switching

+++

### Exercise: Context Switching

+++

### Collections

+++

### Exercise: Creating Collections

+++

### Ad Hoc Displays

+++

### Exercise: Creating an Ad Hoc Display

+++

### Navigation Links

+++

### Exercise: Navigation Links
