@snap[west]
## PI Points and Their Data
@snapend

+++

### PI Points (PI Tags)
@snap[content]
@snap[flex-10]
@ul[text-11](false)
- Data is recorded and stored in PI Data Archive as **PI Points**.
    - Also known as **PI Tags**
- Each PI Point reflects a **single data stream** (i.e. instrument).
@ulend
@snapend
@snapend
@snap[content flex-10]
@snap[flex-10]
![](assets/img/data-archive-to-trend.png)
@snapend
@snapend

+++

### PI System Management Tools (SMT)
@snap[content flex-10]
@snap[flex-10]
PI System Management Tools provides us a way to:
@ul[](false)
- View/modify PI Poin configurations
- Create/delete PI Points
- View/alter PI Point Data
- ...and much more!
@ulend
@snapend
@snap[flex-10 flex-center]
![height=450](assets/img/pi-smt-start.png)
@snapend
@snapend

+++

### Connecting to a PI Data Archive
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-connect-data-archive.png)
@css[text-08](*Note: your PI Data Archive name will likely be different*)
@snapend
@snapend

+++

### Adding a PI Data Archive
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-add-server.gif)
@css[text-08](*Note: your PI Data Archive name will likely be different*)
@snapend
@snapend

+++

### Session Record
@snap[content flex-10 flex-center]
@snap[flex-10]
Errors and status updates are typically shown here.
@ul[](false)
- Connection errors
- Permission errors
- Succesful point creation message
- etc.
@ulend
@snapend
@snap[flex-10 flex-center]
![height=450](assets/img/pi-smt-session-log-error.png)
@snapend
@snapend
+++

### Exercise: Creating a PI Point
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-create-pi-point.gif)
@css[text-08](*Name your PI Point **/<Your Initials/>.Pump01.Discharge Flow Rate**.*)
@snapend
@snapend

+++

### Configuring PI Points

@snap[content]
@snap[flex-10 text-center]
![height=400](assets/img/smt-point-config.png)
The "Point Builder" menu we're in provides us several options for configuring PI Points.
@snapend
@snapend

+++

### Configuring PI Points: General

@snap[content]
@snap[flex-10 text-center]
![height=200](assets/img/smt-point-config-general.png)
@snapend
@snapend
@ul[text-left text-09](false)
- **Name:** Name of the PI Point
- **Descriptor:** Description for the PI Point
- **Stored Values:** Can set whether PI Point contains future data
- **Point Source:** Specifies which PI Interface the PI Point collects data from.
- **Eng Units:** Engineering units for the point.
- **Exdesc:** Extended descriptor (used for some PI Interfaces)
@ulend

+++

### Configuring PI Points: Archive

@snap[content]
@snap[flex-10 text-center]
![height=200](assets/img/smt-point-config-archive.png)
@snapend
@snapend
@ul[text-left text-09](false)
- **Typical value, Zero, Span:** Set reasonable values for Point
- **Scan:** Enable PI Interface to update with data
- **Archiving:** Enable data to be stored to PI Point
- **Compressing:** Enable compression
- **Exception Deviation:** Configure exception
- **Compression Deviation:** Configure compression
@snapend
@snapend

+++

### Exception and Compression
@snap[content]
@snap[flex-10]
Both exception reduce the data that needs to be stored in the Data Archive by strategically leaving some out.
@ul[text-11](false)
- **Exception**
    - Attempts to filter out noise
    - Only passes along values that are different enough from last recorded one
- **Compression**
    - Attempt to keep only meaningful data
    - Drops data that would otherwise be found through interpolation
@ulend
@snapend
@snapend

+++

### Configuring PI Points: Classic

@snap[content]
@snap[flex-10 text-center]
![height=200](assets/img/smt-point-config-classic.png)
@snapend
@snapend
Most of these depend on the PI Interface the PI Point is receiving from. But here what they commonly mean:
@ul[text-left text-09](false)
- **Location 1:** ID of the corresponding PI Interface
- **Location 3:** Scan class number
- **Location 4:** Specifies whether Point should be poll or advise
- **Instrument Tag:** Specifies where to read data from within data source
@ulend
@snapend
@snapend

+++

### Configuring PI Points: Security

@snap[content]
@snap[flex-10 text-center]
![height=200](assets/img/smt-point-config-security.png)
@snapend
@snapend
@snap[content]
@snap[flex-10]
Security can be configured for PI Identities, PI Groups, and PI Users.
Two different security dimensions:
@ul[text-09](false)
- **Point Security:** Who can read/write PI Point configuration
- **Data Security:** Who can read/write PI Point data
@ulend
@snapend
@snapend

+++

### Configuring PI Points: System
@snap[content]
@snap[flex-10 text-center]
![height=200](assets/img/smt-point-config-system.png)
@snapend
@snapend
@snap[content]
@snap[flex-10]
@ul[](false)
- Provides **read-only** information about the PI Point.
- Useful for debugging.
    - Is the PI Point receiving data?
    - Is the PI Point receiving bad values?
    - Who last changed a PI Point?
    - When was the PI Point last changed?
@ulend
@snapend
@snapend

+++

### Searching for Tags in SMT
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-search-pi-points.gif)
@snapend
@snapend

+++

### PI Search Syntax
@snap[content]
@snap[flex-10]
You can search based on several different criteria.
@ul[](false)
- **All** criteria must be met.
- PI only provides **exact matches**.<br>Use "*****" as a wildcard character.
@snapend
@snap[flex-10]
![](assets/img/pi-point-search-syntax.png)
@snapend
@snapend

+++

### Viewing and Modifying Tag Data
@snap[content flex-10 flex-center]
@snap[flex-10 text-center]
@css[text-12](**NOTE**)<br><br>
We need some non-critical data to play with for this course.
To provide this, we will modify data in the Data Archive **directly**.
You will likely **never** do this. Useful data generally comes through more structured routes.<br><br>
@css[green-emphasis text-12](Never do this on production tags!)
@snapend
@snapend

+++

### Viewing and Modifying Historical Tag Data
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-modify-point-data.gif)
@snapend
@snapend

+++

### Viewing Current Tag Data
@snap[content text-center]
@snap[flex-10]
![height=450](assets/img/smt-view-current-values.gif)
@snapend
@snapend
