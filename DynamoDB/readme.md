# Amazon DynamoDB – Detailed Explanation

## What is Amazon DynamoDB?

**Amazon DynamoDB** is a fully managed NoSQL database service provided by Amazon Web Services that allows you to store and retrieve data at high speed with seamless scalability.

It is designed for:

* **Low latency (fast performance)**
* **High scalability**
* **Automatic management (no servers to manage)**

---

## Simple Explanation

Think of DynamoDB as:

> **A super-fast online database that automatically grows with your application**

Unlike traditional databases, you don’t need to:

* Manage servers
* Handle scaling
* Worry about performance tuning

---

# Core Concepts

### 1. Tables

* Data in DynamoDB is stored in **tables**
* Similar to tables in traditional databases

Example:

```
Users
Orders
Products
```

---

### 2. Items

* Each record in a table is called an **item**
* Equivalent to a row in SQL databases

Example:

```
UserID: 101
Name: John
Age: 25
```

---

### 3. Attributes

* Columns in a table are called **attributes**

Example:

```
UserID (Primary Key)
Name
Email
```

---

### 4. Primary Key

Each table must have a **primary key** to uniquely identify items:

#### Types:

* **Partition Key** (Simple Primary Key)
* **Composite Key** (Partition Key + Sort Key)

Example:

```
UserID (Partition Key)
OrderID (Sort Key)
```

---

## How DynamoDB Works

1. Create a table
2. Define primary key
3. Insert items (data)
4. Retrieve data using keys or queries

DynamoDB automatically:

* Distributes data across servers
* Handles scaling
* Maintains performance

---

## Data Access Methods

### 1. GetItem

* Fetch a single item using primary key

### 2. Query

* Retrieve multiple items using partition key

### 3. Scan

* Reads entire table (slow, use carefully)

---

## Indexes

### 1. Global Secondary Index (GSI)

* Allows querying using different attributes

### 2. Local Secondary Index (LSI)

* Same partition key, different sort key

---

## Performance

* Single-digit millisecond latency
* Handles millions of requests per second

---

## Capacity Modes

### 1. On-Demand

* Auto scales
* Pay per request

### 2. Provisioned

* Set read/write capacity manually
* Cheaper for predictable workloads

---

## Security Features

* IAM-based access control
* Encryption at rest and in transit
* Backup and restore

---

## DynamoDB Streams

* Captures changes in table data
* Useful for:

  * Real-time processing
  * Event-driven systems

---

## Transactions

* Supports ACID transactions
* Ensures data consistency

---

## Global Tables

* Multi-region replication
* Low latency worldwide

---

## Common Use Cases

* User profiles
* E-commerce carts
* Gaming leaderboards
* IoT data storage
* Real-time analytics

---

## Advantages

* Fully managed (no server setup)
* Extremely fast
* Highly scalable
* Flexible schema (NoSQL)

---

## Limitations

* Limited complex querying (compared to SQL)
* Requires good design of keys
* Can be expensive if misconfigured

---

## Pricing Basics

You pay for:

* Read and write requests
* Storage used
* Data transfer

---

## Example Item (JSON)

```json
{
  "UserID": "101",
  "Name": "Alice",
  "Email": "alice@example.com"
}
```

---

## Related AWS Services

* EC2 (Compute)
* S3 (Storage)
* Lambda (Serverless)
* API Gateway (APIs)

---

## Summary

Amazon DynamoDB is a high-performance NoSQL database that provides fast and scalable data storage without needing to manage servers.
