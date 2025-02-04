## DataBases
---

### **Data:**

Let's assume you have a `customers` table in **SQL** and a `customers` collection in **MongoDB** with the following data:

- **Customer 1:** John Doe, john@example.com
- **Customer 2:** Jane Smith, jane@example.com

#### **Day 1: Basics of Data Retrieval**

##### **SQL**
**1. Create Database & Table**
```sql
CREATE DATABASE myDB;
USE myDB;

CREATE TABLE customers (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100)
);
```

**2. Insert Data**
```sql
INSERT INTO customers (id, name, email) 
VALUES (1, 'John Doe', 'john@example.com'), 
       (2, 'Jane Smith', 'jane@example.com');
```

**3. Retrieve Data**
```sql
SELECT * FROM customers;
```

##### **MongoDB**
**1. Create Database & Collection**
```sh
use myDB
db.createCollection('customers');
```

**2. Insert Data**
```sh
db.customers.insertMany([
  { name: "John Doe", email: "john@example.com" },
  { name: "Jane Smith", email: "jane@example.com" }
]);
```

**3. Retrieve Data**
```sh
db.customers.find();
```

---

#### **Day 2: Data Filtering and Sorting**

##### **SQL**
**1. Retrieve Data with Filtering (WHERE, AND, OR)**
```sql
SELECT * FROM customers WHERE name = 'John Doe';
```

**2. Retrieve Data with Sorting (ORDER BY)**
```sql
SELECT * FROM customers ORDER BY name ASC;
```

##### **MongoDB**
**1. Retrieve Data with Filtering**
```sh
db.customers.find({ name: 'John Doe' });
```

**2. Retrieve Data with Sorting**
```sh
db.customers.find().sort({ name: 1 }); // 1 for ascending, -1 for descending
```

---

#### **Day 3: Data Insertion, Update, and Deletion**

##### **SQL**
**1. Insert New Data**
```sql
INSERT INTO customers (id, name, email) 
VALUES (3, 'Alice Johnson', 'alice@example.com');
```

**2. Update Data**
```sql
UPDATE customers 
SET email = 'newjohn@example.com' 
WHERE id = 1;
```

**3. Delete Data**
```sql
DELETE FROM customers WHERE id = 2;
```

##### **MongoDB**
**1. Insert New Data**
```sh
db.customers.insertOne({ name: "Alice Johnson", email: "alice@example.com" });
```

**2. Update Data**
```sh
db.customers.updateOne({ name: "John Doe" }, { $set: { email: "newjohn@example.com" } });
```

**3. Delete Data**
```sh
db.customers.deleteOne({ name: "Jane Smith" });
```

---

#### **Day 4: Aggregation and Grouping**

##### **SQL**
**1. Aggregate Function (COUNT)**
```sql
SELECT COUNT(*) FROM customers;
```

**2. Grouping Data (GROUP BY)**
```sql
SELECT email, COUNT(*) FROM customers GROUP BY email;
```

##### **MongoDB**
**1. Aggregate Function (COUNT)**
```sh
db.customers.countDocuments();
```

**2. Grouping Data (Aggregation Pipeline)**
```sh
db.customers.aggregate([
  { $group: { _id: "$email", count: { $sum: 1 } } }
]);
```

---

#### **Day 5: Indexing and Performance**

##### **SQL**
**1. Create Index**
```sql
CREATE INDEX idx_name ON customers (name);
```

**2. View All Indexes**
```sql
SHOW INDEXES FROM customers;
```

##### **MongoDB**
**1. Create Index**
```sh
db.customers.createIndex({ name: 1 });
```

**2. View All Indexes**
```sh
db.customers.getIndexes();
```

---

#### **Day 6: Joins and Lookups**

##### **SQL**
**1. Join Tables (Inner Join)**
Assume you have another table called `orders`.
```sql
CREATE TABLE orders (
  order_id INT PRIMARY KEY,
  customer_id INT,
  amount DECIMAL(10,2),
  FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

Now, you can join the `customers` table with the `orders` table.
```sql
SELECT customers.name, orders.amount
FROM customers
INNER JOIN orders ON customers.id = orders.customer_id;
```

##### **MongoDB**
Since MongoDB is a NoSQL database, there is no concept of joins, but you can achieve similar functionality using `$lookup` in aggregation.

**1. Lookup (Equivalent of SQL Join)**
```sh
db.orders.aggregate([
  { $lookup: {
      from: "customers",
      localField: "customer_id",
      foreignField: "id",
      as: "customerDetails"
    }
  ]
);
```

---

#### **Day 7: Advanced Queries and Subqueries**

##### **SQL**
**1. Subquery in WHERE Clause**
```sql
SELECT name FROM customers WHERE id IN (SELECT customer_id FROM orders WHERE amount > 100);
```

##### **MongoDB**
**1. Subquery (Using `$lookup`)**
```sh
db.orders.aggregate([
  { $lookup: {
      from: "customers",
      localField: "customer_id",
      foreignField: "id",
      as: "customerDetails"
    }
  },
  { $match: { "customerDetails.amount": { $gt: 100 } } }
]);
```

---
