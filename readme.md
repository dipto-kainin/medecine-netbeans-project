# Medicine Management System

## Overview

The Medicine Management System is a Java-based application developed using NetBeans and Java Swing (JFrame) for managing medicine inventory, user data, and order details. This project integrates with a SQL database for storing and retrieving information.

## Features

- User authentication and management (sign up, login, admin access).
- Medicine product management (add, update, delete products).
- Search functionality for medicines.
- Order management (pending orders, user-ordered products).

## Project Structure

### Java Source Files

- **ADMIN.java** / **ADMIN.form**: Admin panel for managing users and products.
- **BUY.java** / **BUY.form**: Interface for users to buy medicines.
- **HOME.java** / **HOME.form**: Home page for the application.
- **MyConnection.java**: Database connection setup.
- **PENDING.java** / **PENDING.form**: Displays pending orders.
- **PENDING_TABLE.java** / **PENDING_TABLE.form**: Table to display pending orders.
- **PRODUCT.java** / **PRODUCT.form**: Manage product details.
- **SEARCH.java** / **SEARCH.form**: Search for products.
- **SIGN_UP.java** / **SIGN_UP.form**: User registration form.
- **USER_LOGIN.java** / **USER_LOGIN.form**: User login form.
- **userOrderedProduct.java** / **userOrderedProduct.form**: Displays products ordered by users.

### Database Files

- **medecine_orderedproduct.sql**: SQL script to create the ordered product table.
- **medecine_productdata.sql**: SQL script to create the product data table.
- **medecine_userdata.sql**: SQL script to create the user data table.

### Images and Icons

Located in the `src/IMAGE` directory, including icons and project-related images used in the application UI.

## Setup and Installation

### Prerequisites

- Java Development Kit (JDK)
- NetBeans IDE
- MySQL Server

### Steps

1. **Clone the Repository**

   ```sh
   git clone <repository_url>
   ```

2. **Open in NetBeans**

   Open NetBeans and load the `MEDICINE` project from the cloned repository.

3. **Set Up the Database**

   - Start your MySQL server.
   - Create a database named `medecine`.
   - Import the SQL scripts located in the `medecinesql` directory:

     ```sh
     mysql -u <username> -p medecine < /path/to/medecine_userdata.sql
     mysql -u <username> -p medecine < /path/to/medecine_productdata.sql
     mysql -u <username> -p medecine < /path/to/medecine_orderedproduct.sql
     ```

4. **Configure Database Connection**

   Update the database connection settings in `MyConnection.java`:

   ```java
   public class MyConnection {
       public static Connection getConnection() {
           Connection con = null;
           try {
               Class.forName("com.mysql.jdbc.Driver");
               con = DriverManager.getConnection("jdbc:mysql://localhost/medecine", "root", "password");
           } catch (Exception ex) {
               System.out.println(ex.getMessage());
           }
           return con;
       }
   }
   ```

5. **Run the Application**

   Build and run the project from NetBeans.

## Usage

1. **Sign Up/Login**: Users can sign up for a new account or log in with existing credentials.
2. **Admin Panel**: Accessible to admin users for managing products and users.
3. **Product Management**: Add, update, or delete medicine products.
4. **Order Management**: View pending orders and user-ordered products.

