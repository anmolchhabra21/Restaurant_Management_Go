# Restaurant Management System using Go, MongoDB, and JWT

The Restaurant Management System is a web application built using Go programming language, MongoDB as the database, and JWT (JSON Web Tokens) for user authentication. The system provides functionalities for managing users, food items, menus, tables, orders, and invoices. Users can register, login, and perform various operations related to restaurant management.

## Features

- **User Management:** Allow users to register and login to the system using JWT authentication.
- **Food Management:** Enable CRUD operations for managing food items available in the restaurant.
- **Menu Management:** Allow creating and updating menus by adding food items to them.
- **Table Management:** Enable CRUD operations for managing restaurant tables.
- **Order Management:** Allow placing orders for specific food items and tables.
- **Invoice Generation:** Generate invoices for completed orders with the details of the food items, quantities, and total amount.

## Installation and Setup

To run the Restaurant Management System, follow these steps:

1. **Install Go:** If you don't have Go installed, download and install it from the official website: https://golang.org/dl/

2. **Install MongoDB:** Install MongoDB on your machine by following the official installation guide: https://docs.mongodb.com/manual/administration/install-community/

3. **Clone the Repository:** Clone or download the Restaurant Management System repository from GitHub to your local machine.

4. **Set Environment Variables:** Create a `.env` file in the project root directory and set the following environment variables:

```
PORT=8000 # Port on which the server will run
SECRET_KEY=your-secret-key # Secret key for JWT token signing
MONGO_URI=mongodb://localhost:27017/your-database-name # MongoDB connection URI
```

5. **Install Dependencies:** Go to the project root directory and run the following command to install the required Go packages:

```
go mod download
```

6. **Run the Server:** Start the server by running the following command in the project root directory:

```
go run main.go
```


The server will start on the specified port (default: 8000), and you can access the Restaurant Management System APIs.

## User Authentication

- The Restaurant Management System uses JWT for user authentication. Users need to register and log in to access the system's features.
- To register a new user, make a `POST` request to `/users/signup` with the required user details (e.g., email, password, first name, and last name).
- To log in, make a `POST` request to `/users/login` with the email and password. Upon successful login, the server will return a signed JWT token and a refresh token.
- The JWT token should be included in the `Authorization` header for all protected routes to access them.

## API Endpoints

- **User Management:**
  - `GET /users`: Get a list of all users.
  - `GET /users/:user_id`: Get details of a specific user.
  - `POST /users/signup`: Register a new user with email, password, first name, and last name.
  - `POST /users/login`: Log in an existing user with email and password.

- **Food Management:**
  - `GET /foods`: Get a list of all food items.
  - `GET /foods/:food_id`: Get details of a specific food item.
  - `POST /foods`: Add a new food item.
  - `PATCH /foods/:food_id`: Update an existing food item.

- **Menu Management:**
  - `GET /menus`: Get a list of all menus.
  - `GET /menus/:menu_id`: Get details of a specific menu.
  - `POST /menus`: Create a new menu.
  - `PATCH /menus/:menu_id`: Update an existing menu.

- **Table Management:**
  - `GET /tables`: Get a list of all tables.
  - `GET /tables/:table_id`: Get details of a specific table.
  - `POST /tables`: Add a new table.
  - `PATCH /tables/:table_id`: Update an existing table.

- **Order Management:**
  - `GET /orders`: Get a list of all orders.
  - `GET /orders/:order_id`: Get details of a specific order.
  - `POST /orders`: Place a new order.
  - `PATCH /orders/:order_id`: Update an existing order.

- **Order Item Management:**
  - `GET /orderItems`: Get a list of all order items.
  - `GET /orderItems/:orderItem_id`: Get details of a specific order item.
  - `GET /orderItems-order/:order_id`: Get order items for a specific order.
  - `POST /orderItems`: Add a new order item.
  - `PATCH /orderItems/:orderItem_id`: Update an existing order item.

- **Invoice Management:**
  - `GET /invoices`: Get a list of all invoices.
  - `GET /invoices/:invoice_id`: Get details of a specific invoice.
  - `POST /invoices`: Generate a new invoice.
  - `PATCH /invoices/:invoice_id`: Update an existing invoice.

## Error Handling

- The system implements proper error handling for API requests, and it returns appropriate HTTP status codes and error messages.

## Security

- The Restaurant Management System uses JWT tokens for user authentication, providing a secure way to access protected routes.
- Make sure to keep the `SECRET_KEY` used for JWT token signing confidential and never expose it publicly.

## Contributing

Contributions to the Restaurant Management System project are welcome! If you find any bugs or want to add new features, please feel free to create issues or submit pull requests on the GitHub repository: [Restaurant Management](https://github.com/anmolchhabra21/Restaurant_Management_Go/)
