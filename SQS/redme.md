# AWS SQS (Simple Queue Service)

##  What is AWS SQS?

AWS SQS (Simple Queue Service) is a **fully managed message queuing service** provided by Amazon Web Services that enables **asynchronous communication** between distributed systems.

It allows different components of an application to communicate by sending and receiving messages through a queue.

---

##  Why Use SQS?

Use SQS when you want to:

* Decouple application components
* Handle asynchronous processing
* Improve system scalability
* Prevent data loss during traffic spikes

---

##  Core Concepts

### 1. Queue

A **queue** is a temporary storage for messages.

Types of queues:

* **Standard Queue**
* **FIFO Queue (First-In-First-Out)**

---

### 2. Producer (Sender)

The **producer** sends messages to the queue.

 Example:

* Order service sends order data to queue

---

### 3. Consumer (Receiver)

The **consumer** retrieves messages from the queue and processes them.

---

### 4. Message

A **message** is the data sent between systems.

* Max size: 256 KB
* Stored until processed

---

### 5. Visibility Timeout

Time during which a message is invisible to other consumers after being read.

---

### 6. Dead Letter Queue (DLQ)

Stores messages that fail processing multiple times.

---

##  How SQS Works

1. Producer sends message to queue
2. Message is stored in queue
3. Consumer polls queue for messages
4. Consumer processes message
5. Message is deleted after successful processing

---

##  Example Workflow

### Order Processing System

1. User places order
2. Order service sends message to SQS
3. Worker service reads message
4. Processes order (payment, inventory, shipping)
5. Deletes message

---

##  Components and Their Tasks

###  Queue

**Task:**

* Stores messages temporarily
* Ensures reliable delivery

---

###  Producer

**Task:**

* Sends messages to queue
* Does not wait for processing

---

###  Consumer

**Task:**

* Polls queue for messages
* Processes and deletes messages

---

###  Message

**Task:**

* Carries data between services

---

###  Visibility Timeout

**Task:**

* Prevents duplicate processing
* Gives time to process message

---

###  Dead Letter Queue (DLQ)

**Task:**

* Stores failed messages
* Helps debugging

---

## Example Architecture

```
[Producer]
     |
     v
   [SQS Queue]
     |
     v
 [Consumer]
```

---

##  Key Features

### Fully Managed

* No server management required

---

###  Reliable Delivery

* Messages are stored redundantly

---

###  Scalable

* Handles unlimited throughput

---

###  Secure

* IAM policies and encryption

---

###  Message Retention

* Messages stored up to 14 days

---

##  Types of Queues

### 1. Standard Queue

* High throughput
* At-least-once delivery
* Best-effort ordering

---

### 2. FIFO Queue

* Exactly-once processing
* Strict message ordering
* Lower throughput

---

##  Use Cases

* Background job processing
* Order processing systems
* Microservices communication
* Batch processing
* Decoupling frontend and backend

---


##  When to Use SQS

Use SQS when:

* You need message buffering
* You want reliable processing
* You need asynchronous workflows
* You want to decouple services

---

##  Limitations

* Requires polling (latency)
* Message size limit (256 KB)
* Duplicate messages possible (Standard Queue)

---
