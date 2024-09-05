<h1>GlassLewis_Assessment</h1>

<u><h3>Overview:</u></h3>

This project is built using ASP.NET Core Web API designed for managing company records. The API offers the following functionalities:

- Swagger URL - https://localhost:7068/swagger/index.html
- UI URL - https://localhost:7068/pages/index.html
- For authentication, I have used Microsoft.AspNetCore.Identity.EntityFrameworkCore which provides common identity services for authentication to support identity bearer tokens and cookies
	- Register User - (https://localhost:7068/register - POST)
 	- Login User - (https://localhost:7068/login - POST)
- Retrieve All Companies: Obtain a list of all company records (https://localhost:7068/api/company/getCompanyCollection - GET)
- Retrieve a Company by ID: Fetch a company record using its unique ID (https://localhost:7068/api/company/getCompanyById/{id} - GET)
- Retrieve a Company by ISIN: Fetch a company record using its ISIN (https://localhost:7068/api/company/getCompanyByIsin/{isin} - GET)
- Create a Company: Add a new company record by specifying the Name, Ticker, Exchange, ISIN, and optionally a Website URL. Each company must have a unique ISIN, and the ISIN's first two characters must be non-numeric 
  (https://localhost:7068/api/company/createCompany - POST)
- Update a Company: Modify the details of an existing company (https://localhost:7068/api/company/updateCompany - PUT)
- This API is built using .NET Core 8, utilizing MS SQL for database operations, and an in-memory database for unit testing.
- Unit testing has been written using xUnit framework.

<u><h3>Steps to Run the Project:</u></h3>
- The project folder GlassLewis_Assessment has the following contents:
 	- GlassLewis_Assessment.sln: Solution file.
	- GlassLewis_Assessment.Api folder: Contains the main project files and static UI page.
	- GlassLewis_Assessment.Api.Tests folder: Contains the unit testing project.
	- Screenshots for reference: UI - Dashboard - Working Screenshot (UI Dashboard) and Swagger - Working Screenshot.jpg (Swagger UI).
- Open the GlassLewis_Assessment.sln solution file.
- Build the application to ensure no compilation errors.
- In Visual Studio, navigate to Tools -> NuGet Package Manager -> Package Manager Console.
- In the Package Manager Console, run `update-database` to create the GlassLewis_Assessment.DB database 
- Verify that the database was created without errors.
- Run the GlassLewis_Assessment application. This will open the Swagger UI at https://localhost:7068/swagger/index.html.
- UI dashboard can be accessed via https://localhost:7068/pages/index.html

<u><h3>Access the API from Swagger:</h3></u>
- In Swagger, start by running the /register POST endpoint to register an user:
	<code>{
	  "email": "string", // should be a valid email address
	  "password": "string"  // Minimum length: 8, must include alphanumeric characters, at least one uppercase letter, and a special character.
	}
   </code>
- After registering, log in with the newly created user credentials using the /login POST endpoint.
  - The login response will include a Bearer token. Copy the token, click the Authorize button in Swagger, and paste the token.
  - The Company API endpoints will now be accessible using the Bearer token.
- Use the CreateCompany API (api/Company/CreateCompany) to add a new company.
- Use the UpdateCompany API (api/Company/UpdateCompany) to edit an existing company record.
- Use the GetCompanyCollection API to retrieve all company records.
- Use the GetCompanyById API to fetch a company record by its ID.
- Use the GetCompanyByIsin API to fetch a company record by its ISIN.
- This setup should guide you through running and testing the Company API effectively.

![Swagger Image](https://github.com/prakashalamanda/GlassLewis_Assessment/blob/master/Swagger%20-%20Dashboard.png)

![Swagger Image](https://github.com/prakashalamanda/GlassLewis_Assessment/blob/master/Swagger%20-%20Authorize.png)

<u><h3>Access the GetCompanyCollection API from UI:</h3></u>
- Navigate to the url - https://localhost:7068/pages/index.html
- Paste the Bearer token generated from the Swagger page in the text area
- Click on 'Get Company details' button to retrieve the company collection

![UI_Image](https://github.com/prakashalamanda/GlassLewis_Assessment/blob/master/UI%20-%20Dashboard.png)

<b>Note - We can also test this from API tools like Postman etc.,</b> 
![UI_Image](https://github.com/prakashalamanda/GlassLewis_Assessment/blob/master/Postman.png)

Thank you!

