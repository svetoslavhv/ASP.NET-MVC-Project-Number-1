

## Laptop Listing System in ASP.NET MVC

You are assigned to design and implement a **Laptop Listing System** where visitors (without authentication) should be able to **view laptop manufacturers** and **laptops** , as well as to **register** and **login** in the system. Registered users (after login) should be able to **comment, vote** and **search** the laptops. **Administrators** should have full **CRUD** operations on **laptops** , **manufacturers** and **comments**. The system should be implemented as server-side Web application in ASP.NET MVC 5.

Problem 1. Laptop System Data Layer

Design a simple data layer to hold **users** , **manufacturers** , **laptops, votes** and **comments**. Each **user** has **username, email** and **password**. The password should be stored in the DB encrypted (not as clear text). **Manufacturers** have **name** (unique and mandatory) and hold a **set of laptops**. Each **laptop** has mandatory **model, monitor** (in inches) **, hard disk** (in GB), **RAM** (in GB), **image** (as url string) and **price** (in Chinese Yuan o.O) and optionally **weight** (in kg), **additional parts** (camera, Bluetooth, etc. as string) and **description** (string). Laptops also have set of **votes** and set of **comments**. Each comment has **user, laptop** and **content**. Each vote has **user** and **laptop**. Fill some sample data in the DB to simplify any further testing.

Use the ASP.NET Identity system to keep the users and their encrypted passwords.

Use **Entity Framework** as ORM engine and **MS SQL Server Local DB** as database storage engine. Your project should run after &quot;copy/paste&quot; deployment, without changing connection strings or other settings. You may use code first, model first or database first approach to access your data from Entity Framework.

Problem 2. Laptop System ASP.NET MVC Application

Design and implement the Laptop System as a server-side web application in ASP.NET MVC. You may use the following steps during your work:

#### Common Features

- **Layout** – design an ASP.NET MVC Layout page to reuse the common page elements like headers and footers and navigation in all other pages in the project.

- Use **Kendo Menu** for the navigation and links to other pages.

- **Configure the ASP.NET Identity System** to enable user management functionality (login / logout). The username should be at least 6 character long.

- **Register user** – by username, password and email the system should be able to register a new user in the system. After successful registration, the user should be redirected to the start page.

#### Public Area

- **Home page** – at the application start page display the top 6 laptops by total votes. Use two rows with three columns and show every laptop&#39;s **manufacturer** , **model** , **image** and **price**.

- **Cache** this page for an hour ahead.

- **View laptop details** – clicking on a laptop from the start page should display all laptop details (manufacturer, model, monitor, hard disk, RAM, image, price and if there are optional fields, display them too) on a separate page.Display all comments for the laptop (no paging is required).

#### User Area

- **List page** – registered users (after login) should be able to see a list page with all the available laptops with **Kendo ListView** and custom template. Display only **manufacturer** , **model** , **image** and **price**.

- Use server side paging (page size 5).

- **Extend laptop details** – Registered users can **comment** and **vote** for the current laptop. **Voting** and **commenting** should be done with **AJAX** updating the information without refreshing the page.

- Comments should not have email addresses in them. Validate it with custom validation attribute.

- **Search** – at the **List** page three search boxes should be displayed. The laptop search results and shows all matching laptops.

Search inputs are:

- By **model** with **Kendo Autocomplete** (server side filtering) 
- By **manufacturer** with **Kendo Dropdown **
- By **price** with **Kendo NumericTextBox **

If some of the inputs are left empty or null, the search should not consider them. The name and model search is containing the substring in the laptop&#39;s name and model. The manufacturer search should search in all categories, if no category is selected.

Searching by empty inputs should return all the laptops.

#### Administration Area

- **Create / edit / delete manufacturers** – successfully logged in administrators should be able to create / edit / delete laptop manufacturers. Use scaffolding. When a manufacturer is deleted all its laptops are deleted as well.

-
  - Ensure your UI behaves correctly when the users enter invalid data, e.g. too long text in a text field or HTML special characters like &quot;&lt;br/&gt;&quot;. Validate the data in your forms.

- **Create / edit / delete laptops** – successfully logged in users should be able to create / edit / delete laptops. Use scaffolding. Optional fields should not be shown in the table. Long column values should be cut to 20 characters ending with &quot;…&quot;. For each laptop in the table there should be &quot;edit&quot; and &quot;delete&quot; buttons. Create and update form should have DropDown list for choosing the laptop manufacturer.


  - Ensure your UI behaves correctly when the users enter invalid data, e.g. too long text in a text field or HTML special characters like &quot;&lt;br/&gt;&quot;. Validate the data in your forms.

- **Create / edit / delete comments** – successfully logged administrators should be able to edit / delete comments.

-
  - Ensure your UI behaves correctly when the users enter invalid data, e.g. too long text in a text field or HTML special characters like &quot;&lt;br/&gt;&quot;. Validate the data in your forms.

- Use **Kendo Grid** with server side paging, sorting and filtering for the comments administration.

#### Other Requirements

- **Error handling** – in case of error (e.g. Internet connection lost, DB connection lost, incorrect request, etc.), an appropriate error message should be displayed. You are free to decide how exactly.

- **User interface (UI)** – the user interface is intuitive, looks nice and is easy-to-use.

- **Repository pattern and Unit of Work** – the data layer is implemented with repository pattern and unit of work.







## Screenshots of the UI

**Home page**


**Details Page**



**Details page for registered users**


**Laptop list page**

 

