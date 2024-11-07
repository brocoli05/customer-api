# Customer-api
This project is a RestAPI built using Laravel to manage customer data, enabling CRUD(Create, Read, Update, Delete) operations on customer records.

## Getting started
Follow the instructions below to set up and run the Customer-api project.

## Environment Requirements
To run this project, ensure you have the following installed:
- Laravel (v9+ recommended)
- PHP (v8.0+)
- Composer (for managing dependencies)
- SQLite

## Project Setup
### 1. Clone the Repository
 ```
 git clone <repository-url>
 cd customer-api
 ```

### 2. Install Dependencies
  ```
  composer install
  ```

### 3. Set Up the Environment
Run the following command to install all required PHP dependencies:
```
cp .env.example .env
```
Update your .env file with any required configurations, such as database connection settings. By default, this API uses an SQLite database.

### 4. Generate an Application Key
  ```
  php artisan key:generate
  ```
### 5. Database Setup

   5.1. Create an SQLite database file by running:
   ```
   touch database/database.sqlite
   ```
   5.2. Update your `.env` file with the following database settings:
   ```
   DB_CONNECTION=sqlite
   DB_DATABASE=database/database.sqlite
   ```
   5.3. Run the migrations to create the necessary tables:
   ```
   php artisan migrate
   ```

## Running the Server
To start the Laravel development server, use the following command:
```
php artisan serve
```
The server will start at `http://127.0.0.1:8000` by default. Visit this URL in your browser or use a tool like Postman to interact with the API.


## API Endpoinst
### 1. List All Customers
- URL: /api/customers
- Method: GET
- Response: Returns a JSON array of all customers.

### 2. Get a Specific Customer
- URL: /api/customers/{id}
- Method: GET
- Response: Returns JSON data of a specific customer.
- 404 Error if customer not found.

### 3. Create a New Customer
- URL: /api/customers
- Method: POST
- Body: JSON object with name and email.
- Response: Returns the created customer data.
- Validation Errors: If data is invalid, returns validation errors.

### 4. Update a Customer
- URL: /api/customers/{id}
- Method: PUT/PATCH
- Body: JSON object with name and/or email.
- Response: Returns the updated customer data.
- 404 Error if customer not found.

### 5. Delete a Customer
- URL: /api/customers/{id}
- Method: DELETE
- Response: Returns a success message.
- 404 Error if customer not found.
