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


&nbsp;
### 04 AddBookModel migration

* `PM> add-migration AddBookModel`
* `PM> update-database`


&nbsp;
### 05 BooksController

* Controlers -> add -> Controller -> MVC Controller - Empty, name -> BooksController
* Add a constructor and associate the *ApplicationDbContext*.
* Add code for the disposal of the db object.
* Set the view to return a list of books from the db.


&nbsp;
### 06 Books Index View

* Right click on the *Index* action method and add the *Views/Books/Index.cshtml* view.
* Tie the view to an IEnumerable of books model.
* Add a *Create New* button using tag-helpers and Bootstrap classes.
* Add custom CSS classes in *wwwroot/css/site.css* and use them in the html code to display the book list.
* Use html-helpers in the Razor code which loops through and displays the model items.
* Use tag-helpers to display the *Edit* and *Delete* buttons.
