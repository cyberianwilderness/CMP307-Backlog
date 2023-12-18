
[Link to Backlog](https://github.com/cyberianwilderness/CMP307-Backlog/issues)
## Progress from previous work block:
- [x] Insert new software asset table into SQL
- [x] Insert new hardwaresoftwareassociation table into SQL
- [x] Test data from new sql details appear
- [x] Amend Functional and Non Functional requirements
- [ ] Remove textboxes that are highlighted when a form is loaded
- [ ] Data Sanitisation needs to be put in please
- [x] System needs to read the current date
- [x] Amend deleting a hardware asset or software asset and the impact this will have on the hardwaresoftwareassociation - will need to be deleted from the hardwaresoftwareassociation table first.

### Immediate Priorities:
- [ ] Remove textboxes that are highlighted when a form is loaded
- [x] Software AssetCRUD Interface
- [x] Software Asset Management Interface
- [x] Asset Type Selector Interface
- [x] Asset Type Selector Implementation
- [x] Read in contents of Software Asset Table
- [x] Employee CRUD form

### Secondary Tasks (If Time Permits)
- [x] Data Sanitisation needs to be put in please (Validate function added)
- [ ] Remove textboxes that are highlighted when a form is loaded

  
## Additional Notes: [If required]


```sql
USE SCOTTISHGLEN

CREATE TABLE SCOTTISHGLEN.SoftwareAsset (
    SoftwareAssetID INT PRIMARY KEY IDENTITY(1,1),
    OSSystemName NVARCHAR(255),
    OSSystemVersion NVARCHAR(50),
    OSSystemManufacturer NVARCHAR(255),
   
);
INSERT INTO SoftwareAsset (OSSystemName, OSSystemVersion, OSSystemManufacturer) 
VALUES ('Windows 10', '10.0', 'Microsoft');



```

```sql
CREATE TABLE SCOTTISHGLEN.HardwareSoftwareAssociation (
    HardwareAssetID INT,
    SoftwareAssetID INT,
    InstallDate DATE,
    PRIMARY KEY (HardwareAssetID, SoftwareAssetID),
    FOREIGN KEY (HardwareAssetID) REFERENCES SCOTTISHGLEN.Asset(AssetID),
    FOREIGN KEY (SoftwareAssetID) REFERENCES SCOTTISHGLEN.SoftwareAsset(SoftwareAssetID)
);
INSERT INTO SCOTTISHGLEN.HardwareSoftwareAssociation (HardwareAssetID, SoftwareAssetID, InstallDate)
VALUES (2, 1, '12-11-2023');
     

```
If the user is in the **information technology department**, they can perform vulerability checks
will allow the information technology department to ac