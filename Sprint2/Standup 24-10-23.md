## Progress from previous work block:

- [x] Create examples of asset data
- [ ] Option add another asset once one asset has been added
- [ ] Allow the user to add a new asset
- [ ] Allow the user to delete an asset
- [x] Test that navigation between forms functions as desires, rectifying any issues
- [x] Create an interface for adding a new product.
- [x] Drop table employeeassetallocation

Plan for Today/Next Work Block:
### Immediate Priorities:
- [x] Create use case diagram first draft
- [x] Allow the user to add a new asset
- [ ] Allow the user to delete an asset
- [x] Create class diagram.
- [x] New sprint
- [ ] Screenshots of Kanban boards for final report
- [x] Option add another asset once one asset has been added
### Secondary Tasks (If Time Permits)
- [ ] 
       
![[Pasted image 20231023121844.png]]

|   |   |
|---|---|
 
|System|Weather station|
| --- | ----- |
|Use case|Report weather|
|Actors|Weather information system, Weather station|
|Description|The weather station sends a summary of the weather data that has been collected from the instruments in the collection period to the weather information system. The data sent are the maximum, minimum, and average ground and air temperatures; the maximum, minimum, and average air pressures; the maximum, minimum, and average wind speeds; the total rainfall; and the wind direction as sampled at five-minute intervals.|
|Stimulus|The weather information system establishes a satellite communication link with the weather station and requests transmission of the data.|
|Response|The summarized data is sent to the weather information system.|
|Comments|Weather stations are usually asked to report once per hour but this frequency may differ from one station to another and may be modified in the future.|

create interface diagram for
login
finder
employee
help
asset
department

![[Pasted image 20231023130256.png]]
## Additional Notes: [If required]



```SQL

USE SCOTTISHGLENN

CREATE TABLE SCOTTISHGLEN.Department

INSERT INTO SCOTTISHGLEN.Department
VALUES
('Sales'), 
('Information Technology'),
('Operations'),
('Human Resources'),
('Finance')
;
```

```sql
CREATE TABLE SCOTTISHGLEN.Employee 
( 
	EmployeeID INT IDENTITY(1,1) PRIMARY KEY,
	Forename VARCHAR(50), 
	Surname VARCHAR(50), 
	Email VARCHAR(50), 
	DepartmentID INT FOREIGN KEY REFERENCES SCOTTISHGLEN.Department(DepartmentID) 
); 
```

```SQL

INSERT INTO SCOTTISHGLEN.Employee (Forename, Surname, Email, DepartmentID) 
VALUES 
('Ben', 'Foster', 'ben.foster@scottishglen.co.uk', 1),
('Allan', 'McGregor', 'allan.mcgregor@scottishglen.co.uk', 1),
('Julian', 'Speroni', 'julian.speroni@scottishglen.co.uk', 1),
('Craig', 'Gordon', 'craig.gordon@scottishglen.co.uk', 1),
('Jamie', 'MacDonald', 'jamie.macdonald@scottishglen.co.uk', 1),

('Ryan', 'Shawcross', 'ryan.shawcross@scottishglen.co.uk', 2),
('Tony', 'Hibbert', 'tony.hibbert@scottishglen.co.uk', 2),
('David', 'Wheater', 'david.wheater@scottishglen.co.uk', 2),
('Jonny', 'Evans', 'jonny.evans@scottishglen.co.uk', 2),
('Alex', 'Scott', 'alex.scott@scottishglen.co.uk', 2),
('Steph', 'Houghton', 'steph.houghton@scottishglen.co.uk', 2),
('Steven', 'Taylor', 'steven.taylor@scottishglen.co.uk', 2),
('Kieran', 'Gibbs', 'kieran.gibbs@scottishglen.co.uk', 2),
('Lee', 'Wallace', 'lee.wallace@scottishglen.co.uk', 2),
('Lewis', 'Stevenson', 'lewis.stevenson@scottishglen.co.uk', 2),

('James', 'Morrison', 'james.morrison@scottishglen.co.uk', 3),
('Mark', 'Noble', 'mark.noble@scottishglen.co.uk', 3),
('Craig', 'Gardner', 'craig.gardner@scottishglen.co.uk', 3),
('Jill', 'Scott', 'jill.scott@scottishglen.co.uk', 3),
('Fara', 'Williams', 'fara.williams@scottishglen.co.uk', 3),
('Lee', 'Cattermole', 'lee.cattermole@scottishglen.co.uk', 3),
('Grant', 'Leadbitter', 'grant.leadbitter@scottishglen.co.uk', 3),
('Jack', 'Rodwell', 'jack.rodwell@scottishglen.co.uk', 3),
('Scott', 'Arfield', 'scott.arfield@scottishglen.co.uk', 3),
('David', 'Dunn', 'david.dunn@scottishglen.co.uk', 3),

('Leon', 'Osman', 'leon.osman@scottishglen.co.uk', 4),
('Matt', 'Jarvis', 'matt.jarvis@scottishglen.co.uk', 4),
('Karen', 'Carney', 'karen.carney@scottishglen.co.uk', 4),
('Nikita', 'Parris', 'nikita.parris@scottishglen.co.uk', 4),
('Rachel', 'Yankey', 'rachel.yankey@scottishglen.co.uk', 4),
('Matthew', 'Etherington', 'matthew.etherington@scottishglen.co.uk', 4),
('Chris', 'Brunt', 'chris.brunt@scottishglen.co.uk', 4),
('Ryan', 'Kent', 'ryan.kent@scottishglen.co.uk', 4),

('Eniola', 'Aluko', 'eniola.aluko@scottishglen.co.uk', 5),
('Toni', 'Duggan', 'toni.duggan@scottishglen.co.uk', 5),
('Ellen', 'White', 'ellen.white@scottishglen.co.uk', 5),
('Grant', 'Holt', 'grant.holt@scottishglen.co.uk', 5),
('Jodie', 'Taylor', 'jodie.taylor@scottishglen.co.uk', 5),
('Kyle', 'Lafferty', 'kyle.lafferty@scottishglen.co.uk', 5);


```


```SQL

CREATE TABLE SCOTTISHGLEN.Asset
( 
	AssetID INT IDENTITY(1,1) PRIMARY KEY, 
	SystemName VARCHAR(50), 
	Model VARCHAR(50), 
	Manufacturer VARCHAR(50), 
	Type VARCHAR(50), 
	IPAddress VARCHAR(15), 
	PurchaseDate DATE, 
	Notes TEXT, 
	EmployeeID INT FOREIGN KEY REFERENCES SCOTTISHGLEN.Employee(EmployeeID), 
);

```

```SQL
CREATE TABLE SCOTTISHGLEN.Department 
(
    DepartmentID INT IDENTITY(1,1) PRIMARY KEY,
    DepartmentName VARCHAR(50)
);
```

``` SQL
CREATE TABLE SCOTTISHGLEN.EmployeeAssetAllocation
(
    AllocationID INT IDENTITY(1,1) PRIMARY KEY,
    AssetID INT FOREIGN KEY REFERENCES SCOTTISHGLEN.Asset(AssetID),
    EmployeeID INT FOREIGN KEY REFERENCES SCOTTISHGLEN.Employee(EmployeeID)
);

```