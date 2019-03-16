# Create a Employee table in Azure Data Studio

*The following tutorial is based on this [Microsoft article](https://docs.microsoft.com/de-de/sql/azure-data-studio/quickstart-sql-database?view=sql-server-2017).*

Create a customers table with the following variables in [schema](https://docs.microsoft.com/de-de/dotnet/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server) `dbo`: 

- Employee_ID
- Employee_Nr Personalnummer 	varchar(10) 	Pflicht 	eindeutig
- Name 	varchar(30) 	Pflicht 	 
- firstName 	varchar(30) 	Pflicht 	 
- Birthdate 	date 	Pflicht 	 
- phoneTelefon 	varchar(30) 	optional 	 
- Email 	varchar(50) 	optional 	 
- office_nr 	varchar(10) 	optional

and set the variable `EmployeeId`as the primary key column.

### Create a table

1) Right-click on your Azure Data Studio in the SERVERS sidebar and select New Query.
2) Paste this SQL into the query editor.

```{sql}
CREATE TABLE dbo.Employee
(
   EmployeeId   INT NOT NULL PRIMARY KEY,
   Employee_Nr  [NVARCHAR](10)  NOT NULL,
   Name         [NVARCHAR](50)  NOT NULL,
   FirstName    [NVARCHAR](50)  NOT NULL,
   Phone        [NVARCHAR](50)  NOT NULL,
   Email        [NVARCHAR](50)  NOT NULL,
   OfficeNr     int             NOT NULL,
);
GO
```

3) From the toolbar, select Run. Notifications appear in the MESSAGES pane showing query progress.


### View the result

Finally, we want to select rows from table 'Customers'. Therefore, replace the previous query with this one and select Run. 

```{sql}
SELECT * FROM dbo.Employee;
```

