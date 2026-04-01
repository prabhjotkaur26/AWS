# AWS Lambda

## What is AWS Lambda?

**AWS Lambda** is a serverless compute service provided by Amazon Web Services that allows you to run code **without managing servers**.

You just:

* Write your code
* Upload it
* Lambda runs it automatically when triggered

---

## Simple Explanation

Think of Lambda as:

>  **A function that runs in the cloud only when needed**

You don’t need to:

* Create servers
* Manage infrastructure
* Worry about scaling

---

## Core Concept: Function

### What is a Lambda Function?

A **Lambda function** is:

* A small piece of code
* Designed to perform a specific task
* Runs only when triggered

Example:

* Resize an image
* Send an email
* Process data

---

## How Lambda Works (Step-by-Step)

1. Write a function (in Python, Node.js, etc.)
2. Upload it to Lambda
3. Configure a trigger
4. When the trigger happens → function runs
5. Lambda automatically scales and executes

---

## Event-Driven Execution

Lambda works on **events (triggers)**

### Common Triggers:

* File upload in S3
* HTTP request via API Gateway
* Database change (DynamoDB)
* Scheduled time (cron jobs)

---

## Example Flow

👉 Upload image → S3
👉 S3 triggers Lambda
👉 Lambda resizes image
👉 Stores new image back in S3

---

## Example Lambda Function (Python)

```python
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Hello from Lambda!'
    }
```

---

## Supported Languages

* Python
* Node.js
* Java
* Go
* C#
* Ruby

---

## Execution Model

### Key Features:

* Runs only when triggered
* Maximum execution time: **15 minutes**
* Stateless (does not remember previous runs)

---

## Components of Lambda

### 1. Handler

* Entry point of the function

### 2. Event

* Input data to the function

### 3. Context

* Runtime information (memory, time, request ID)

---

## Scaling

* Automatically scales based on number of requests
* Can handle **thousands of executions simultaneously**

---

## Memory & CPU

* You can configure memory (128 MB to 10 GB)
* CPU power increases with memory

---

## Security

### 1. IAM Role

* Lambda uses IAM roles to access other AWS services

### 2. Permissions

* Define what Lambda can do (e.g., read S3, write DynamoDB)

---

## Lambda Layers

* Used to share code (libraries, dependencies)
* Helps reduce duplication

---

## Monitoring & Logging

* Integrated with CloudWatch
* Logs every execution
* Helps debug errors

---

## Versioning & Aliases

* Version control for functions
* Aliases for environments (dev, prod)

---

## Common Use Cases

* Backend APIs
* File processing
* Real-time data processing
* Automation tasks
* Chatbots
* IoT applications

---

## Advantages

* No server management
* Auto scaling
* Pay only for execution time
* Easy integration with AWS services

---

## Limitations

* Cold start latency
* Max execution time (15 min)
* Stateless nature
* Debugging can be harder

---

## Pricing

You pay for:

* Number of requests
* Execution time (milliseconds)
* Memory used

---

## Integration with AWS Services

Lambda works closely with:

* S3 → File triggers
* DynamoDB → Data streams
* API Gateway → REST APIs
* CloudWatch → Monitoring

---

## Real-Life Example

When a user uploads a profile picture:

1. Image goes to S3
2. Lambda resizes it
3. Saves thumbnail
4. Updates database

---

## Summary

AWS Lambda lets you run code in response to events without managing servers, making it ideal for scalable and event-driven application.
