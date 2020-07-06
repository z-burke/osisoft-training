@snap[west]
## PI Asset Framework Overview
@snapend

+++

### Asset Framework
@snap[null]
Asset framework organizes a collection of tags into a **hiearchy of assets**.
@snapend
@snap[content]
@snap[flex-10]
@ul[](false)
- **Assets** are represented by **elements**.
- **Data streams** (PI Tags) pertaining to those elements are represented by **attributes**.
@ulend
@snapend
@snap[flex-16]
![](assets/img/element-to-attribute.png)
@snapend
@snapend

+++

### PI System Explorer (SE)
@snap[content]
@snap[flex-10]
PI System Explorer provides us a way to:
@ul[](false)
- View/modify AF Hierarchies
- Connect to outside data sources
- Create AF Analyses
- Generate AF Notifications
- ...and much more!
@ulend
@snapend
@snap[flex-10 text-center]
![height=500](assets/img/pse-start-menu.png)
@snapend
@snapend

+++

### Connections to AF Servers and Data Archives
@snap[content]
@snap[flex-10]
Two types of connections:
<ul class style="list-style-type: none;">
<li><img src="assets/img/icons/data-archive.png" style="margin: 0 10px 0 10px; height: 1em;" />Data Archive</li>
<li><img src="assets/img/icons/af-server.png" style="margin: 0 10px 0 10px; height: 1em;" />AF Server</li>
</ul>
Each of these can have a status:
<ul class style="list-style-type: none;">
<li><img src="assets/img/icons/connected.png" style="margin: 0 10px 0 10px; height: 1em;" />Connected</li>
<li><img src="assets/img/icons/default.png" style="margin: 0 10px 0 10px; height: 1em;" />Default</li>
</ul>
@snapend
@snap[flex-10]
![](assets/img/pse-server-connections.png)
@snapend
@snapend

+++

### Adding an AF Server
@snap[content]
@snap[flex-10 text-center]
![height=450](assets/img/pse-server-connection-add.png)
@css[text-09](*Put the name of your AF Server as "Host"*)
@snapend
@snapend

+++

### Tabs in PI System Explorer
@snap[content]
@snap[flex-10]
@ul[text-09](false)
- **Elements**<br>Asset hierarchy
- **Event Frames**<br>Recorded Event Frames
- **Library**<br>Templates, tables, enum sets, etc.
- **Unit of Measure**<br>The database that stores UOM
- **Contacts**<br>Used for PI Notifications
- **Management**<br>List of AF Analyses
@ulend
@snapend
@snap[flex-10]
![](assets/img/pi-system-explorer-tabs.png)
@snapend
@snapend

+++

### Asset Framework Databases
@snap[content]
@snap[flex-10]
@ul[](false)
- AF Databases provide **isolation between AF hierarchies**.
- Can have multiple AF Databases on an individual AF Server.
- AF Databases on the same server will still have access to the same:
    - PI Points
    - UOM's
@ulend
@snapend
@snap[flex-10 flex-center-y]
![](assets/img/pse-databases.png)
@snapend
@snapend

+++

### Asset Framework Elements
@snap[content]
@snap[flex-10]
**AF Elements** can be thought of as a folder in which data streams can be grouped together.
@snapend
@snapend
@snap[content]
@snap[flex-10]
@ul[](false)
- **Assets** are often **Elements**<br>*i.e. pumps, compressors*
- However, **groupings of assets** can be Elements as well
    - Forms a grouping of Elements
    - Can also have contain tags of their own
- **Sub-components** of assets are sometimes Elements as well.<br>*i.e. pump motors*
@ulend
@snapend
@snap[flex-10 flex-center-y]
![](assets/img/pse-af-elements.png)
@snapend
@snapend


+++

### Asset Framework Attributes
@snap[content]
@snap[flex-10]
**AF Attributes** are the **data streams** that are associated with **AF Elements**.
@snapend
@snapend
@snap[content]
@snap[flex-10]
@ul[](false)
- These data streams are often **PI Points**, but they can also be things like:
    - Static **metadata**
    - Inputs from **AF Tables**
    - Results of **calculations**
- Notice that AF Attributes can have **child Attributes** of their own.
@ulend
@snapend
@snap[flex-10 flex-center-y]
![](assets/img/pse-af-attributes.png)
@snapend
@snapend

+++

### Setting a Query Time
@snap[content]
@snap[flex-10]
Remember that PI Points contain timeseries data...
..but AF shows you a single value for attributes.
You are seeing a **snapshot** of the data. Change your view by setting the **query time**.
@snapend
@snap[flex-10]
![](assets/img/pse-querytime.png)
@snapend
@snapend

+++

### Viewing Attribute Data
@snap[content]
@snap[flex-10]
Right-click on an attribute to bring up the following options for visualizing data:
@ul[](false)
- **Trend**<br>View a graph of attribute data over time (supports multiple attributes).
- **Time-series**<br>Provides a table of attribute data along with some interesting statistics.
@ulend
PSE is not primarily a visualization tool, but this feature is useful!
@snapend
@snap[flex-10]
![](assets/img/pse-viewing-data.png)
@snapend
@snapend

+++

### Viewing PI Points in PSE
@snap[content flex-10]
@snap[flex-10]
PSE provides a way to search for PI Points.
From here you can see:
@ul[](false)
- Configuration information
- Timeseries data and trends
@ulend
@snapend
@snap[flex-10 flex-center]
![](assets/img/pse-tag-search.png)
@snapend
@snapend

+++

### Asset Framework's Transaction Model
@snap[content]
@snap[flex-10]
With many people touching the same AF Database, how do we prevent them from making conflicting changes?
@snapend
@snapend
@snap[content flex-10]
@snap[flex-10 flex-center]
![height=250](assets/img/af-transaction-model.png)
@snapend
@snapend

+++

### Asset Framework's Transaction Model
@snap[content]
@snap[flex-10]
@ul[text-11](false)
- This transaction model **largely revolves around AF Elements**:
    - checking them out
    - making changes to them
    - checking them back in (or reverting)
- Attributes and analyses are not checked out (their **elements** are).
- Other objects we'll cover here can be checked out as well (tables, templates, etc.).
@ulend
@snapend
@snapend

+++

### Asset Framework's Transaction Model
@snap[content]
@snap[flex-10]
@ul[text-11](false)
- Elements' transaction status can be see in the AF Hiearchy
    - **Current user has checked out**<br>(Check in to save changes)
    - **Another user has checked out**<br>(Cannot make changes)
@ulend
@snapend
@snap[flex-10]
![](assets/img/pse-checked-out-elements-example.png)
@snapend
@snapend

+++

### AF: More Than Just Organization
@snap[content]
@snap[flex-10]
Asset Framework provides more than just organization:
@ul[](false)
- Allows for **inclusion of metadata** for assets and their data.
- Coupled with an **analysis engine** for performing calculations on attribute data.
- Allows for connecting **more than just tag data** into PI (i.e. SQL data)
@ulend
@snapend
@snapend