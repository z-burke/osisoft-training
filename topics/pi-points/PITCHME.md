@snap[west]
## PI Points and Their Data
@snapend

+++

### PI Points
@snap[content]
@snap[content-10]
Data is recorded and stored in PI Data Archive as PI Points.
Each PI Point reflects a single data stream (i.e. instrument).
![](assets\img\data-archive-to-trend.png)
@snapend
@snapend

+++

### PI System Management Tools (SMT)
@snap[content]
@snap[content-10]
PI System Management Tools provides us a way to:
@ul[](false)
- View/modify PI Poin configurations
- Create/delete PI Points
- View/alter PI Point Data
- ...and much more!
@ulend
@snapend
@snap[content-10]
![height=400](assets\img\pi-smt-start.png)
@snapend
@snapend

+++

### Connecting to a PI Data Archive
@snap[content text-center]
@snap[content-10]
![height=400](assets\img\smt-connect-data-archive.png)
@snapend
@snapend
@snap[south span-100]
@css[text-08](*Note: your PI Data Archive name will likely be different*)
@snapend

+++

### Adding a PI Data Archive
@snap[content text-center]
@snap[content-10]
![height=450](assets\img\smt-add-server.gif)
@snapend
@snapend
@snap[south span-100]
@css[text-08](*Note: your PI Data Archive name will likely be different*)
@snapend

+++

### Session Record
@snap[content]
@snap[content-10]
Errors and status updates are typically shown here.
@ul[](false)
- Connection errors
- Permission errors
- Succesful point creation message
- etc.
@snapend
@snap[content-10]
![height=450](assets\img\pi-smt-session-log-error.png)
@snapend
@snapend
+++

### Exercise: Creating a PI Point
@snap[content text-center]
@snap[content-10]
![height=450](assets\img\smt-create-pi-point.gif)
@snapend
@snapend
@snap[south span-100]
@css[text-08](*Name your PI Point **\<Your Initials\>.Pump01.Discharge Flow Rate**.*)
@snapend

+++

### Configuring PI Points

@snap[content]
@snap[content-10]
The "Point Builder" menu we're in provides us several options for configuring PI Points.
![height=400](assets\img\smt-point-config.png)
@snapend
@snapend

+++

### Configuring PI Points: General

@snap[content]
@snap[content-10]
![height=200](assets\img\smt-point-config-general.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Configuring PI Points: Archive

@snap[content]
@snap[content-10]
![height=200](assets\img\smt-point-config-archive.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Exception and Compression

+++

### Configuring PI Points: Classic

@snap[content]
@snap[content-10]
![height=200](assets\img\smt-point-config-classic.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Configuring PI Points: Security

@snap[content]
@snap[content-10]
![height=200](assets\img\smt-point-config-security.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Configuring PI Points: System

@snap[content]
@snap[content-10]
![height=200](assets\img\smt-point-config-system.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Searching for Tags in SMT
@snap[content text-center]
@snap[content-10]
![height=450](assets\img\smt-search-pi-points.gif)
@snapend
@snapend
@snap[south span-100]
@snapend

+++

### PI Search Syntax
@snap[content]
@snap[content-10]
You can search based on several different criteria.
Each critieria is "AND" together.
PI only provides **exact matches**. Get around this by using "*", which acts as a wildcard character.
@snapend
@snap[content-10]
![height=450](assets\img\smt-tag-search.gif)
@snapend
@snapend
@snap[south span-100]
@snapend

+++

### Viewing and Modifying Tag Data
@snap[content]
@snap[content-10 text-center]
<br>
**NOTE**
We generally only use this method to view tag data for troubleshooting tag data.
But here we will update tag values ourselves.
Normally, this data would be sent to tags from PI Interfaces and we would never modify this data.
This is just so we have data to play with.
@snapend
@snapend

+++

### Viewing and Modifying Historical Tag Data
@snap[content text-center]
@snap[content-10]
![height=450](assets\img\smt-modify-point-data.gif)
@snapend
@snapend
@snap[south span-100]
@snapend

+++

### Viewing Current Tag Data
@snap[content text-center]
@snap[content-10]
![height=450](assets\img\smt-view-current-values.gif)
@snapend
@snapend
@snap[south span-100]
@snapend
+++
