# Information about EntityFramework and EntityFrameworkCore
Hello, Thanks for being here.

This repository mainly provides information about what really required about Entityframework and Entityframeworkcore for any developers. One place to get information for all your needs w.r.t these.

We provide information in this repository in the form of requirement based,

**Ex:** Your application should allow users to store information in the backend and they asked you to integrate SQL Server using EntityframeworkCore ORM.

**Note:** I am not going to cover any concepts from these but I will try to give you alternative approaches and the importance of the code.

You will find all the below requirements on this _**entity framework core**_ from the following repository,

**One more important point here is,**

For any EF Core projects, there is one base Package we have to install,

**Package Name: Microsoft.EntityFrameworkCore by _Microsoft_**

[Demos On EntityFrameowrk](https://github.com/nuthanm/EntityFrameworkCoreDemos)

//TODO - C# and SQL SERVER datatype matches

### **Requirement 1:** 
Author: Trevoir Williams

Course: Entity Framework Core - A Full Tour

Platform: Udemy

1. Use _**code First Approach**_, Create Entities/Models/Classes first and this generates a table using migration script.
   - **Remember**: First create dependencies Models first
2. Use SQL Server as data provider to store all this information
   - If you are installing Microsoft.EntityFrameworkCore.Sqlserver by Microsoft then the base EF Core library is going to install.
3. Using the Migrations script, we generate the database and objects along with migration versions
   - Install Nuget Package: Microsoft.EntityFrameworkCore.Tools, this is for migration
   - Run using .bat file or using Package Manager Console
     - First thing, we should select the project where the DB Context file resides
     - _**Commands to run**_
     - > **get-help entityframework** => gives what leverages we do with this entity-framework
     - > **add-migration <NameOftheMigration>** Ex: add-migration InitialMigration
       - It creates a migration folder and it contains files that we use these to generate database objects,
       - Method: **up** updates the database
       - Method: **down** drops the objects
     - > **update-database**
     - After a successful run, then we can verify the database with all necessary objects in our SQL server
  4. If you want to achieve the same thing using SQL script to automate/one click/one execution then follow the same,


**Questions in the interview:**

1. Create a project that should connect with EFCore SQL Server to perform Curd Operations
2. I would like to know what all required to start and how to write and configure all these
3. Can you create architecture for this simple project?
4. What files are required?
   - Create necessary Models/Domains/Entities
   - Create dbContext and configure these models
   - Migration required
     - **Option 1:**Use add and update migration commands
     - **Option 2:** use script-migration and it generates SQL script to run directly in DB.
5. What is the difference between the data first vs the code first approach?
   - code first => use add & update migration scripts
   - data first => use Scaffold-Dbcontext
     Ex: > Scaffold-DbContext -provider Microsoft.EntityFrameworkCore.SqlServer -connection "<DBConnectionString>"
     **Note:** In your connection string contains "\\" then replace with "\"
     - This generates DB context, models in the project
     - 


### References
TODO

### Useful Extensions
1. In Visual Studio, Under extensions:
   - "EF Core Power Tools" => **View Diagram** = Helps in visualizing our database objects. After this successful installation we not need to go and see the same in SSMS.
      - Sometimes we don't have access to create or view ER diagrams using SSMS in that case this option is really helpful
        
**Screenshot:**

![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/6568a81e-4f3a-44e1-883d-a8d4077025d6)

**Before installation:**

![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/567a865e-13d1-4166-8ea9-1ecd15c25a32)

**Note:**Once it is downloaded VS requires to restart and then you can find this option in the project context menu.

**Installer**
![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/82fc175c-4396-478e-a992-547d58070e54)


**After Installation:**
_Context menu looks like below,_
![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/409c8021-4718-4729-bb86-584d711d3b5d)
![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/e175f204-3f06-4590-98b9-1d8928e403b4)



**Adding Verbose Logging to EF Core's Workload**:

**Code:**
optionsBuilder.UseSqlServer("Data Source=(localdb)\\MSSQLLocalDB;Initial Catalog=FootballLeague_EfCore")
              .LogTo(Console.WriteLine, new[] { DbLoggerCategory.Database.Command.Name }, LogLevel.Information)
              .EnableSensitiveDataLogging();
              
**EnableSensitiveDataLogging()** => As per the above code, we are logging the query and its data in the console window this way we can see what values we are passing, and helps during debugging.

_**Sample log message(s)**_
![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/4a23ddbc-a62e-497d-8d24-ea9c0d26f91e)
![image](https://github.com/nuthanm/Infoaboutentityframework/assets/29816449/15672564-7a5b-4136-90ce-1807f0a0ae08)



  
