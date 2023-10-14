
[Link to Backlog](https://github.com/cyberianwilderness/CMP307-Backlog/issues)
## Progress from previous work block:
- [x] Analyse Mock Data provided by Dr J.O 
- [x] : Updating Visual studio for full desired functionality
- [x] Read over assessment and submit assignment
- [x] Create Login Page
- [x] Establish workflow where work can be push and pulled into the repository on github classroom
 
## Blockers
| Blocker | What do I need to unlock this? |
| --- | ------------ |
| Uploading frame may impact the functionality of my visual studio solution file| Dialogue with J.Ophoff in class dicussing best place to store mockups on Github |
| Cannot Authenticate with firewall | Credentials to be reset by IT services |
| Unsure where to store my standups | Discussion with J.Ophoff required |

  ---
  
## Plan for Today/Next Work Block:

### Immediate Priorities:
- [x] Create schema on Abertay database server
- [ ] Department Page
- [x] Help Page
- [x] Dashboard Page
- [ ] False data on assets to check with J.O during week 4 lab
- [ ] Create new Sprint Kanban board
- [ ] Read UML chapter

### Secondary Tasks (If Time Permits)
- [ ] Start week 4 practical tasks
- [ ] [UML Tutorial - Use Case, Activity, Class and Sequence Diagrams - Essential Software Modeling](https://www.youtube.com/watch?v=RMuMz5hQMf4)
- [ ] [UML 2.0 Tutorial](https://www.youtube.com/watch?v=OkC7HKtiZC0)
       

## Additional Notes: [If required]


USE SCOTTISHGLEN;

CREATE TABLE Departments 
(
    DepartmentID INT PRIMARY KEY AUTO_INCREMENT,
    DepartmentName VARCHAR(50)
);

INSERT INTO SCOTTISHGLEN.Departments (DepartmentName) 
VALUES
('Sales'), # 1
('Information Technology'), #2
('Operations'), #3
('Human Resources'), #4
('Finance'); #5
	
CREATE TABLE 
Employees 
( 
	EmployeeID INT PRIMARY KEY AUTO_INCREMENT, 
	FirstName VARCHAR(50), 
	LastName VARCHAR(50), 
	Email VARCHAR(50), 
	DepartmentID INT, FOREIGN KEY REFERENCES SCOTTISHGLENN.Departments(DepartmentID) 
); 

```
SQL
INSERT INTO Employees (FirstName, LastName, Email, DepartmentID) VALUES 
('Ben', 'Foster', 'ben.foster@scottishglen.co.uk', 1),
('Carly', 'Telford', 'carly.telford@scottishglen.co.uk', 1),
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
('Kyle', 'Lafferty', 'kyle.lafferty@scottishglen.co.uk', 5),
('Paul', 'McGowan', 'paul.mcgowan@scottishglen.co.uk', 5);

```


CREATE TABLE 
Assets 
( 
	AssetID INT PRIMARY KEY AUTO_INCREMENT, 
	SystemName VARCHAR(50), 
	Model VARCHAR(50), 
	Manufacturer VARCHAR(50), 
	Type VARCHAR(50), 
	IPAddress VARCHAR(15), 
	PurchaseDate DATE, 
	Notes TEXT, 
	EmployeeID INT, FOREIGN KEY REFERENCES SCOTTISHGLEN.Employees(EmployeeID),
	DepartmentID INT, FOREIGN KEY REFERENCES SCOTTISHGLEN.Departments(DepartmentID)
);






```SQL

1.  James   Morrison (Central Midfielder)    james.morrison@scottishglen.co.uk        Operations
2.  Ryan    Shawcross (Defender)             ryan.shawcross@scottishglen.co.uk       Information Technology
3.  Mark    Noble (Central Midfielder)       mark.noble@scottishglen.co.uk           Operations
4.  Leon    Osman (Winger)                   leon.osman@scottishglen.co.uk           Human Resources
5.  Ben     Foster (Goalkeeper)              ben.foster@scottishglen.co.uk           Sales
6.  Danny   Simpson (Defender)               danny.simpson@scottishglen.co.uk        Information Technology
7.  Matt    Jarvis (Winger)                  matt.jarvis@scottishglen.co.uk          Human Resources
8.  Craig   Gardner (Central Midfielder)     craig.gardner@scottishglen.co.uk        Operations
9.  David   Wheater (Defender)               david.wheater@scottishglen.co.uk        Information Technology
10. Jonny   Evans (Defender)                 jonny.evans@scottishglen.co.uk          Information Technology
11. Karen   Carney (Winger)                  karen.carney@scottishglen.co.uk         Human Resources
12. Alex    Scott (Defender)                 alex.scott@scottishglen.co.uk           Information Technology
13. Eniola  Aluko (Striker)                  eniola.aluko@scottishglen.co.uk         Finance
14. Jill    Scott (Central Midfielder)       jill.scott@scottishglen.co.uk           Operations
15. Toni    Duggan (Striker)                 toni.duggan@scottishglen.co.uk          Finance
16. Steph   Houghton (Defender)              steph.houghton@scottishglen.co.uk       Information Technology
17. Nikita  Parris (Winger)                  nikita.parris@scottishglen.co.uk        Human Resources
18. Fara    Williams (Central Midfielder)    fara.williams@scottishglen.co.uk        Operations
19. Lucy    Bronze (Defender)                lucy.bronze@scottishglen.co.uk          Information Technology
20. Jordan  Nobbs (Central Midfielder)       jordan.nobbs@scottishglen.co.uk         Operations
21. James   Collins (Defender)               james.collins@scottishglen.co.uk        Information Technology
22. Jack    Rodwell (Central Midfielder)     jack.rodwell@scottishglen.co.uk         Operations
23. Ellen   White (Striker)                  ellen.white@scottishglen.co.uk          Finance
24. Rachel  Yankey (Winger)                  rachel.yankey@scottishglen.co.uk        Human Resources
25. Grant   Holt (Striker)                   grant.holt@scottishglen.co.uk           Finance
26. Gabby   Agbonlahor (Striker)             gabby.agbonlahor@scottishglen.co.uk     Finance
27. Sophie  Ingle (Defender)                 sophie.ingle@scottishglen.co.uk         Information Technology
28. Katie   Chapman (Central Midfielder)     katie.chapman@scottishglen.co.uk        Operations
29. Karen   Bardsley (Goalkeeper)            karen.bardsley@scottishglen.co.uk       Sales
30. Mary    Earps (Goalkeeper)               mary.earps@scottishglen.co.uk           Sales
...
50. David   Dunn (Central Midfielder)        david.dunn@scottishglen.co.uk           Operations
51. Joey    Barton (Central Midfielder)      joey.barton@scottishglen.co.uk          Operations
52. Jodie   Taylor (Striker)                 jodie.taylor@scottishglen.co.uk         Finance
53. Demi    Stokes (Defender)                demi.stokes@scottishglen.co.uk          Information Technology
54. Steven  Taylor (Defender)                steven.taylor@scottishglen.co.uk        Information Technology
55. Matthew Etherington (Winger)             matthew.etherington@scottishglen.co.uk  Human Resources
56. Millie  Bright (Defender)                millie.bright@scottishglen.co.uk        Information Technology
57. Chris   Brunt (Winger)                   chris.brunt@scottishglen.co.uk          Human Resources
58. Kieran  Gibbs (Defender)                 kieran.gibbs@scottishglen.co.uk         Information Technology
59. Keira   Walsh (Central Midfielder)       keira.walsh@scottishglen.co.uk          Operations
60. Carly   Telford (Goalkeeper)             carly.telford@scottishglen.co.uk        Sales


```