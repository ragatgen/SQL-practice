The SQL script is building a basic online supermarket database from scratch. It performs three main operations: create the database, create the products table, and populate it with sample inventory.

1. Create the database
   ```bash
CREATE DATABASE OnlineStore;
```
This creates a new PostgreSQL database named OnlineStore. Think of the database as the container that will hold all tables, data, and future store information.

After this runs, you connect pgAdmin to that database before executing the remaining commands.

2. Create the products table

   ```bash
CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    category VARCHAR(100),
    product_name VARCHAR(150),
    price NUMERIC(10,2)
);
```

This creates a table named products.

Column breakdown:
id SERIAL PRIMARY KEY
Auto-generates a unique number for each product.
Example: 1, 2, 3, 4...
PRIMARY KEY means no duplicates and identifies each row uniquely.
category VARCHAR(100)
Stores the department/category.
Example: Fruits, Dairy, Bakery.
product_name VARCHAR(150)
Stores the product name.
Example: Apple, Milk 1L, Frozen Pizza.
price NUMERIC(10,2)
Stores money values with decimals.
Example: 2.50, 10.99

10,2 means:

up to 10 digits total
2 digits after decimal
3. Insert products
INSERT INTO products (category, product_name, price)
VALUES ...

This loads the table with many supermarket items.

Example:
```bash
('Fruits', 'Apple', 0.50)
```
Means:

id	category	product_name	price
auto	Fruits	Apple	0.50

Every line inserts another product.

4. Query the products
   ```bash
SELECT * FROM products
ORDER BY category, product_name;
```
This retrieves all products and sorts them:

By category alphabetically
Then by product name alphabetically

So you would see:

Bakery first, then Dairy, Fruits, etc.

Real-world meaning

This simulates the backend product catalog for an online supermarket.

Examples of usage:

Show products on website
Search by category
Build shopping cart
Display prices
Generate receipts
Inventory management (future enhancement)
