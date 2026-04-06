# AWS SNS (Simple Notification Service)

## What is AWS SNS?

AWS SNS (Simple Notification Service) is a **fully managed messaging service** provided by Amazon Web Services that enables **pub/sub (publisher-subscriber)** communication between distributed systems.

It allows you to send messages to multiple subscribers instantly and reliably.

---

##  Why Use SNS?

SNS is used when you want to:

* Send notifications to multiple systems/users
* Decouple microservices
* Broadcast messages in real-time
* Build event-driven architectures

---

## Core Concepts

### 1. Topic

A **topic** is a communication channel where messages are sent.

* Publishers send messages to a topic
* Subscribers receive messages from the topic

 Think of it as a **broadcast channel**

---

### 2. Publisher

The **publisher** is the service or application that sends messages to a topic.

 Example:

* Order service publishes "Order Placed" event

---

### 3. Subscriber

A **subscriber** is an endpoint that receives messages from a topic.

Supported subscriber types:

* AWS Lambda
* SQS Queue
* Email
* SMS
* HTTP/HTTPS endpoints

---

### 4. Subscription

A **subscription** connects a topic to a subscriber.

Each subscription defines:

* Protocol (email, Lambda, SQS, etc.)
* Endpoint (where message is sent)

---

##  How SNS Works

1. Create a Topic
2. Add Subscribers (create subscriptions)
3. Publisher sends a message to the topic
4. SNS delivers the message to all subscribers

---

##  Example Workflow

### Order Notification System

1. Order is placed
2. Publisher sends message to SNS Topic
3. SNS distributes message to:

   * Email service → sends confirmation email
   * Lambda → processes order
   * SQS → queues order for backend processing

---

##  Components and Their Tasks

###  Topic

**Task:**

* Receives messages from publishers
* Distributes messages to all subscribers

---

###  Publisher

**Task:**

* Sends messages/events to SNS topic
* Does NOT know who the subscribers are

---

###  Subscriber

**Task:**

* Receives messages from SNS
* Performs specific actions based on message

---

###  Subscription

**Task:**

* Connects topic and subscriber
* Defines how messages are delivered

---

###  Message Filtering (Optional)

**Task:**

* Ensures only relevant messages are delivered to subscribers
* Uses filter policies

---

## Example (Architecture Flow)

```
[Publisher]
     |
     v
[SNS Topic]
  /   |    \
 v    v     v
Email Lambda SQS
```

---

##  Example Code (Publish Message)

```javascript id="u82k2p"
const AWS = require('aws-sdk');
const sns = new AWS.SNS();

const params = {
  Message: 'Order Placed Successfully',
  TopicArn: 'arn:aws:sns:region:account-id:order-topic'
};

sns.publish(params, (err, data) => {
  if (err) console.error(err);
  else console.log('Message sent:', data);
});
```

---

##  Key Features

### Pub/Sub Messaging

* One-to-many communication model

---

###  Real-Time Notifications

* Instant delivery to subscribers

---

### High Availability

* Fully managed and fault-tolerant

---

### Security

* IAM policies
* Encryption with AWS KMS

---

###  Message Filtering

* Deliver messages selectively

---

##  Use Cases

* Application alerts and notifications
* Order processing systems
* Event-driven microservices
* Fan-out architecture (send to multiple services)
* Monitoring and logging alerts

---

##  When to Use SNS

Use SNS when:

* You need to send the same message to multiple services
* You want real-time notifications
* You are building event-driven systems

---

##  Limitations

* No message persistence like SQS (unless combined)
* Message size limit (256 KB)
* Requires proper subscription management

---

