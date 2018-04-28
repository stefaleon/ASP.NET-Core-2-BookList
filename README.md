## BookList
### an ASP.NET Core 2 basic app

### from [The complete ASP.NET MVC Core 2.0 Course ](https://www.udemy.com/the-complete-aspnet-mvc-core-20-course/)
### by [Bhrugen Patel](https://www.udemy.com/user/bhrugenpatel/)


&nbsp;
### 00 Start project

* new project -> ASP.NET Core Web Application, name -> BookList
* Web Application(MVC), No Authentication, target ASP.NET Core 2.0


&nbsp;
### 01 Book model

* Add *Book.cs* to *Models*.


&nbsp;
### 02 ApplicationDbContext

* Add the *ApplicationDbContext* class.
* Add the *Books* DbSet to it.


&nbsp;
### 03 Connection String

* In *Startup.cs*, add the *AddDbContext* service.
* Define the connection string in *appsettings.json*.
