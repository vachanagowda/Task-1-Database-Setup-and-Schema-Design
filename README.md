# Task 1 - Database Setup: EcommerceDB

## Objective
Create a relational database for an e-commerce platform with proper tables, relationships, and constraints.

## Database Schema
The EcommerceDB contains the following tables:

1. **Categories**
   - `category_id` (PK, int, auto-increment)
   - `category_name` (varchar(100), unique)
   - **Purpose:** Stores product categories.

2. **Products**
   - `product_id` (PK, int, auto-increment)
   - `product_name` (varchar(100))
   - `price` (decimal(10,2))
   - `stock` (int, default 0)
   - `category_id` (FK → Categories.category_id)
   - **Purpose:** Stores product details and category association.

3. **Customers**
   - `customer_id` (PK, int, auto-increment)
   - `customer_name` (varchar(100))
   - `customer_email` (varchar(100), unique)
   - `customer_phone` (varchar(15))
   - `customer_address` (varchar(255))
   - **Purpose:** Stores customer details.

4. **Orders**
   - `order_id` (PK, int, auto-increment)
   - `customer_id` (FK → Customers.customer_id)
   - `order_date` (date)
   - `status` (varchar(50), default 'Pending')
   - **Purpose:** Stores orders placed by customers.

5. **OrderItems**
   - `order_id` (PK, FK → Orders.order_id)
   - `product_id` (PK, FK → Products.product_id)
   - `quantity` (int)
   - `price` (decimal(10,2))
   - **Purpose:** Stores individual items in an order.

---

## Relationships
- **Categories → Products:** One-to-Many
- **Products → OrderItems:** One-to-Many
- **Orders → OrderItems:** One-to-Many
- **Customers → Orders:** One-to-Many

---

## Tools Used
- Microsoft SQL Server / SSMS
- SQL scripts

---

## Outcome
- Database schema successfully created with all tables, primary keys, foreign keys, and default values.
- Ready for inserting sample data and performing queries.
- Provides a solid foundation for e-commerce application development.
