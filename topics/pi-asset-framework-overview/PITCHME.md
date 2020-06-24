@snap[west]
## PI Asset Framework Overview
@snapend

+++

### Asset Framework
@snap[null]
Asset framework organizes a collection of tags into a **hiearchy of assets**.
@snapend
@snap[content]
@snap[content-10]
@ul[text-08](false)
- **Assets** are represented by **elements**.
- **Data streams** (PI Tags) pertaining to those elements are represented by **attributes**.
@ulend
@snapend
@snap[content-12]
![](assets/img/element-to-attribute.png)
@snapend
@snapend

+++

### Connections to AF Servers and Data Archives in PSE
@snap[content]
@snap[content-10]
Two types of connections:
@ul[text-08](false)
- Data Archive
- AF Server
@ulend
Each of these can have a status:
@ul[text-08](false)
- Connected
- Default
@ulend
@snapend
@snap[content-10]
![](assets/img/pse-server-connections.png)
@snapend
@snapend

+++

### Tabs in PI System Explorer
@snap[content]
@snap[content-10]
@ul[text-07](false)
- **Elements**<br>Asset hierarchy
- **Event Frames**<br>Recorded Event Frames
- **Library**<br>Templates, tables, enum sets, etc.
- **Unit of Measure**<br>The database that stores UOM
- **Contacts**<br>Used for PI Notifications
- **Management**<br>List of AF Analyses
@ulend
@snapend
@snap[content-10 flex-center-y]
![IMAGE](assets/img/pi-system-explorer-tabs.png)
@snapend
@snapend

+++

### Asset Framework Databases
@snap[content]
@snap[content-10]
@ul[text-08](false)
- AF DAtabases provide **isolation between AF hierarchies**.
- Can have multiple AF Databases on an individual AF Server.
- AF Databases on the same server will still have access to the same:
    - PI Points
    - UOM's
@ulend
@snapend
@snap[content-10 flex-center-y]
![](assets/img/pse-databases.png)
@snapend
@snapend

+++

@snap[north-west]
### Viewing Attribute Data
@snap[span-50]
Right-click on an attribute to bring up the following options for visualizing data:
@ul[text-08](false)
- **Trend**<br>View a graph of attribute data over time (supports multiple attributes).
- **Time-series**<br>Provides a table of attribute data along with some interesting statistics.
@ulend
PSE is not primarily a visualization tool, but this feature is useful!
@snapend
@snap[east span-50]
<br><br><br><br>
![IMAGE](assets/img/pse-viewing-data.png)
@snapend


+++

@snap[north-west]
### Setting a Query Time
@snap[span-50]
Remember that PI Points contain timeseries data...
@snap[text-right]
..but AF shows you a single value for attributes.
@snapend
You are seeing a **snapshot** of the data. Change your view by setting the **query time**.
@snapend
@snapend
@snap[east span-45]
<br><br><br>
![IMAGE](assets/img/pse-querytime.png)
@snapend

+++

@snap[north-west]
### Viewing PI Points in PSE
@snap[span-50]
PSE provides a way to search for PI Points.
From here you can see:
@ul[text-08](false)
- Configuration information
- Timeseries data and trends
@ulend
@snapend
@snapend
@snap[east span-55]
<br><br><br><br>
![IMAGE](assets/img/pse-tag-search.png)
@snapend

+++

@snap[north-west]
### Asset Framework's Transaction Model
@css[text-center](With many people touching the same AF Database, how do we prevent them from making conflicting changes?)
@snapend
@snap[south span-100]
![height=250](assets/img/af-transaction-model.png)
@snapend

+++

@snap[north-west]
### Asset Framework's Transaction Model
@ul[text-09](false)
- This transaction model **largely revolves around AF Elements**:
    - checking them out
    - making changes to them
    - checking them back in (or reverting)
- Attributes and analyses are not checked out (their **elements** are).
- Other objects we'll cover here can be checked out as well (tables, templates, etc.).
@ulend
@snapend

+++

@snap[north-west]
### Asset Framework's Transaction Model
@ul[text-09 span-50](false)
- Elements' transaction status can be see in the AF Hiearchy
    - **Current user has checked out**<br>(Check in to save changes)
    - **Another user has checked out**<br>(Cannot make changes)
@ulend
@snapend
@snap[east]
<br><br><br>
![IMAGE](assets/img/pse-checked-out-elements-example.png)
@snapend

+++

@snap[north-west]
### Asset Framework - More Than Just Organization
Asset Framework provides more than just organization:
@ul[](false)
- Allows for inclusion of metadata for assets and their data.
- Coupled with an analysis engine for performing calculations on attribute data.
- Allows for connecting more than just tag data into PI (i.e. SQL data)