# AWS IAM User

## What is an IAM User?

An **IAM User (Identity and Access Management User)** is an identity created in Amazon Web Services that represents a person or application that interacts with AWS services.

It is used to:

* Authenticate (log in to AWS)
* Get permissions to access AWS resources

---

## Simple Explanation

Think of an IAM User as:

> 👤 **A login account for AWS with specific permissions**

Just like you create users in a system, IAM allows you to:

* Create multiple users
* Give each user different access rights

---

## Core Components of an IAM User

### 1. Username

* Unique name for the user in your AWS account

Example:

```
john-admin
developer-1
```

---

### 2. Credentials

IAM users can have different ways to log in:

#### a. Password

* Used to log in to AWS Management Console (web)

#### b. Access Keys

* Used for programmatic access (CLI, SDK)

Example:

```
Access Key ID
Secret Access Key
```

---

### 3. Permissions

* Define what the user can and cannot do

Permissions are given using:

* Policies
* Groups
* Roles

---

## Permissions in Detail

### 1. IAM Policies

* JSON documents that define permissions

Example:

```json
{
  "Effect": "Allow",
  "Action": "s3:ListBucket",
  "Resource": "*"
}
```

---

### 2. Groups

* Collection of IAM users
* Apply permissions to multiple users at once

Example:

* Admin group
* Developer group

---

### 3. Roles (Difference from User)

* Roles are temporary identities
* IAM users are permanent identities

---

## How IAM User Works

1. Create IAM user
2. Assign permissions (policy/group)
3. Provide credentials
4. User logs in or accesses AWS
5. AWS checks permissions before allowing actions

---

## Types of Access

### 1. Console Access

* Login via browser
* Uses username + password

### 2. Programmatic Access

* Access via:

  * AWS CLI
  * SDKs (Python, Java, etc.)

---

## Security Best Practices

### 1. Use Least Privilege

* Give only necessary permissions

### 2. Enable MFA (Multi-Factor Authentication)

* Adds extra security layer

### 3. Rotate Access Keys

* Regularly update credentials

### 4. Avoid Using Root User

* Use IAM users instead

---

## Real-Life Example

In a company:

* Admin → Full access
* Developer → Access to EC2 and S3
* Analyst → Read-only access

Each person gets their own IAM user with specific permissions.

---

## Common Use Cases

* Team member access management
* Application authentication
* Secure access to AWS services
* Managing permissions in organizations

---

## Advantages

* Fine-grained access control
* Improved security
* Easy user management
* Integration with all AWS services

---

## Limitations

* Requires proper configuration
* Misconfigured permissions can cause security risks

---

## IAM User vs Root User

| Feature  | Root User | IAM User               |
| -------- | --------- | ---------------------- |
| Access   | Full      | Limited (configurable) |
| Usage    | Rare      | Daily use              |
| Security | High risk | Safer                  |

---

## Summary

IAM Users help you securely control access to AWS resources by assigning specific permissions to different users.
