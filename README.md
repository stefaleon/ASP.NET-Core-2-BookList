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


&nbsp;
### 07 Display the Books navbar link

* Edit *_Layout.cshtml*. Remove the *Home*, *About* and *Contact* links and display the *Books* link which points to the *Index* action of the *Books* controller.


&nbsp;
### 08 Add the *Create* GET and POST action methods 

* Add the *Create* GET action method which will return the relevant view.
* Add the *Create* POST action method. Use the *HttpPost* and *ValidateAntiForgeryToken* attributes.
* The POST method returns an async Task which redirects to the *Index* action after saving the new book in the db. If the model state is not valid, it returns the view and passes the received book object.


&nbsp;
### 09 Make the *Name* property required

* Use data annotations in the model to make the book name required.
* Add a migration and update the database.


&nbsp;
### 10 Add the *Create* View

* Right click on the *Create* action method and add the *Views/Books/Create.cshtml* view.
* Tie the view to a *Book* model.
* Add a form. Use tag-helpers for the form-action, validation, labels and inputs and style with Bootstrap classes.
* Add the *Create* and *Back* button styled inputs.


&nbsp;
### 11 Add the *Details* action and view

* Add the *Details* GET action method. It takes a book id parameter and returns an async Task which displays the view of the specific book or appropriate error messages.
* Right click on the *Details* action method and add the *Views/Books/Details.cshtml* view.
* Tie the view to a *Book* model.
* Display the book name in a disabled input tag.
* Display the *Edit* and *Back To List* button styled links.
* Use tag-helpers in order to get the links to call the appropriate actions and route the *Edit* link to the proper book id.


&nbsp;
### 12 Add the *Edit* and *Delete* GET action methods

* Add the *Edit* and *Delete* GET action methods by making copies of the code for the *Details* action.


&nbsp;
### 13 Add the *Edit* POST action method

* The *Edit* POST method uses the *HttpPost* and *ValidateAntiForgeryToken* attributes.
* It takes two parameters, a book id and a book object. 
* Checks for matching of the id parameter with the book object id.
* It returns an async Task which redirects to the *Index* action after updating the book in the db. 
* If the model state is not valid, it returns the view and passes the received book object.



&nbsp;
### 14 Add the *Delete* POST action method

* Has the *HttpPost* and *ValidateAntiForgeryToken* attributes.
* We can name it anything if we include the *ActionName* attribute and set it to *Delete*.
* Takes an id parameter.
* Finds the book object that matches the id and removes it from the db.
* Returns an async Task which redirects to the *Index* action.



&nbsp;
### 15 Add the *Edit* and *Delete* views

* Add the *Edit* view. Copy the code of the *Create* view. Direct the form asp-action to the *Edit* action and adjust the button text accordingly.
* Create the *Delete* view as another copy and make the appropriate adjustments. Direct to the *Delete* action, rid of validation, edit and style the buttons and disable the input for the book name.