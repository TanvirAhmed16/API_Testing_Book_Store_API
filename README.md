
# Book Store API Testing Using Postman

Welcome to the Book Store API Testing Guide. It's a complete API Testing Project from an interactive 
document (Swagger UI link- ), a demo Book Store API along with report generated using newman.

- API Link : https://bookstore.toolsqa.com/swagger/?fbclid=IwAR32DOU6xAY

### User Account

To test the API, first you will need to create a user 
account, generate an API token and authenticate the 
created user. Follow these steps to get started:
- Make a POST request to the endpoint **/User** with a request body containing the following fields using JSON data format:
    
    - **`userName`**: The desired username for the new user (required)
    - **`password`**: The desired password for the new user (required)

-	After creating a user, you need to generate an API token by making a POST request to the endpoint **/GenerateToken** with a request body containing the following fields:
    - **`userName`**: The username of the user (required)
    - **`Password`**: The password of the user (required)

-	To authenticate your API requests, include the API token in the Authorization header of your request. The value of the header should be in the format **Bearer <token>**.

-	You can now make requests to the API as the authenticated user. Please note that certain endpoints may require additional permissions, which can be granted to the user by an administrator.

### Book Store
After successful authentication of the user, API allows 
users to retrieve a list of books, add new books to the 
user list, update book details, and delete books.

- To get started, you will need to make a GET request to the endpoint **/Books** to retrieve a list of all the books in the store. This endpoint accepts no parameters. The response will be a JSON array of book objects, each containing the following fields:
    - **`isbn`**: A unique identifier for the book
    - **`title`**: The title of the book
    - **`subtitle`**: The subtitle of the book
    - **`author`**: The author of the book
    - **`publish_date`**: Publish date of the book
    - **`pages`**: Total number of pages of the book
    - **`description`**: A short description of the book
    - **`website`**: A link to get the book
- To add a new book to the authenticated user book list, you will need to make a POST request to the endpoint **/Books**. The request body should be a JSON object containing the following fields:
    - **`userId`**: The userid of the authenticated user (required)
    - **`isbn`**: The isbn number of the book (required)
- To update a book's details, you will need to make a PUT request to the endpoint **/Books/{isbn}**, where **{isbn}** is the unique identifier of the book. The request body should be a JSON object containing the fields you wish to update. 
    - **`userId`**: The userid of the authenticated user (required)
    - **`isbn`**: The isbn number of the book (required)
- To delete a book from the store, you will need to make a DELETE request to the endpoint **/Books**. The request body should be a JSON object containing the fields you wish to update. 
    - **`isbn`**: The isbn number of the book (required)
    - **`userId`**: The userid of the authenticated user (required)
- To get any particular book details from the store, you will need to make a GET request to the endpoint **/Books?ISBN={Books_ISBN}** where **ISBN** is the parameter for that particular book.

- And finally to delete the user, you will need to make a DELETE request to the endpoint **/User/{{U_ID}}** where **U_ID** is the userid of that particular user.

- I have also executed some pre-request scripts and test validations/assertions to the API requests, and at the end of everything I have generated an advanced html format report for the API using newman.

Please note that all requests to the API must include 
a valid API key in the Authorization header.

### Tools Used
- Postman
- newman


## Report Screenshots

![App Screenshot-1](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-1.JPG?raw=true "Summary")

![App Screenshot-2](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-2.JPG?raw=true "Passed Tests")

![App Screenshot-3](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-3.JPG?raw=true "Failed Tests")

![App Screenshot-4](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-4.JPG?raw=true "Skip Tests")

![App Screenshot-5](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-5.JPG?raw=true "Test Details")

![App Screenshot-6](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-6.JPG?raw=true "Test Details")

![App Screenshot-7](https://github.com/TanvirAhmed16/API_Testing_Book_Store_API_Using_Postman/blob/main/Report%20SS/Report%20SS-7.JPG?raw=true "Test Details")

That's all. Thank You...
