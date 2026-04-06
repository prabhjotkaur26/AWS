# AWS SSO (AWS IAM Identity Center)

## What is AWS SSO?

AWS SSO (Single Sign-On), now called **AWS IAM Identity Center**, is a service that allows you to **centrally manage access to multiple AWS accounts and applications using a single login**.

It eliminates the need to manage multiple usernames and passwords.

---

## Why Use AWS SSO?

Use AWS SSO when you want to:

* Provide one login for multiple AWS accounts
* Manage user access centrally
* Integrate with corporate identity providers
* Improve security and user experience

---

## Core Concepts

### 1. Identity Source

The system where users are managed.

Types:

* AWS Identity Center directory (default)
* External Identity Provider (e.g., Active Directory, Okta)

---

### 2. Users

People who need access to AWS resources.

---

### 3. Groups

Collection of users with similar access needs.

---

### 4. Permission Sets

A **permission set** defines what a user can do in an AWS account.

 Similar to IAM roles

---

### 5. AWS Accounts

Multiple AWS accounts managed under AWS Organizations.

---

### 6. Applications

Third-party or custom apps integrated with SSO.

---

##  How AWS SSO Works

1. User logs in via SSO portal
2. Identity is verified
3. User selects AWS account
4. Permission set is applied
5. Temporary credentials are granted

---

## Example Workflow

### Multi-Account Access System

1. Company has 3 AWS accounts:

   * Dev
   * Test
   * Production

2. Admin:

   * Creates users and groups
   * Assigns permission sets

3. User logs in once

4. Accesses all accounts without re-login

---

## Components and Their Tasks

###  Identity Source

**Task:**

* Authenticates users
* Stores user credentials

---

###  User

**Task:**

* Logs into SSO portal
* Accesses assigned resources

---

###  Group

**Task:**

* Organizes users
* Simplifies permission management

---

###  Permission Set

**Task:**

* Defines access permissions
* Grants roles in AWS accounts

---

###  AWS Account

**Task:**

* Hosts resources (EC2, S3, etc.)
* Receives access via SSO

---

###  SSO Portal

**Task:**

* Provides a central login dashboard
* Displays accessible accounts/apps

---

##  Example Architecture

```id="k2l9qp"
        [User]
          |
          v
     [SSO Portal]
          |
          v
   [Identity Center]
          |
   -----------------
   |       |       |
 [Dev]   [Test]  [Prod]
```

---

##  Key Features

###  Single Login

* One username and password for all accounts

---

###  Centralized Access Control

* Manage permissions from one place

---

### Temporary Credentials

* No long-term access keys required

---

### Integration Support

* Works with:

  * Active Directory
  * SAML 2.0 providers
  * External identity providers

---

### Audit & Monitoring

* Tracks user access and activity

---

## Use Cases

* Enterprise multi-account management
* Secure developer access
* Centralized authentication system
* SaaS application integration
* DevOps team access control

---

##  When to Use AWS SSO

Use AWS SSO when:

* You manage multiple AWS accounts
* You want centralized authentication
* You need enterprise-grade access control
* You want to integrate with external identity systems

---

## Limitations

* Initial setup complexity
* Requires AWS Organizations for full benefits
* Learning curve for permission sets

---
