
[Link to Backlog](https://github.com/cyberianwilderness/CMP307-Backlog/issues)
## Progress from previous work block:
- [x] Create schema on Abertay database server
- [ ] Department Page
- [x] Help Page
- [x] Dashboard Page
- [x] False data on assets to check with J.O during week 4 lab
- [ ] Create new Sprint Kanban board
- [x] Read UML chapter

### Secondary Tasks (If Time Permits)
- [ ]
 Yesterday/Tasks from Last Work Block:
  
## Blockers
Challenge 1: No known blockers at present
   
## Plan for Today/Next Work Block:
### Immediate Priorities:
- [ ] [UML Tutorial - Use Case, Activity, Class and Sequence Diagrams - Essential Software Modeling](https://www.youtube.com/watch?v=RMuMz5hQMf4)
- [ ] [UML 2.0 Tutorial](https://www.youtube.com/watch?v=OkC7HKtiZC0)
- [x] Create new Sprint Kanban board
- [x] Department Page
- [x] Asset Looker Page UI
- [x] Asset Finder Page
- [x] Get application to read host PC information.

### Secondary Tasks (If Time Permits)
- [ ] Get one table to test if asset lookup works and that database is connected to app correctly.
       

## Additional Notes: [If required]

future task - email erd and tables to jacques

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