# Amazon EC2 (Elastic Compute Cloud) – Easy Explanation

## What is Amazon EC2?

**Amazon EC2 (Elastic Compute Cloud)** is a service provided by Amazon Web Services that lets you rent virtual computers (servers) in the cloud.

---

## Simple Explanation

Think of EC2 as:

>  **A computer you can rent online**

Instead of buying a physical computer or server, you:

* Create a virtual machine
* Run applications on it
* Pay only for the time you use it

---

## Key Concepts

### 1. Instance

* A virtual computer in the cloud
* Called an **EC2 instance**

You can:

* Start it
* Stop it
* Restart it

---

### 2. AMI (Amazon Machine Image)

* A pre-configured template
* Contains:

  * Operating System (Linux, Windows)
  * Software

Example:

* Ubuntu Server
* Windows Server

---

### 3. Instance Types

Different sizes of computers depending on need:

| Type  | Use Case            |
| ----- | ------------------- |
| t2/t3 | Small apps, testing |
| m5    | General purpose     |
| c5    | High CPU work       |
| r5    | High memory apps    |

---

### 4. Storage (EBS)

* EC2 uses disks called **Elastic Block Store (EBS)**
* Works like a hard drive

---

### 5. Security Groups

* Acts like a **firewall**
* Controls:

  * Who can access your instance
  * Which ports are open (e.g., 22 for SSH, 80 for web)

---

## How EC2 Works (Step-by-Step)

1. Choose an AMI (OS)
2. Select instance type
3. Configure storage and network
4. Launch instance
5. Connect using SSH or Remote Desktop

---

## Real-Life Example

If you want to host a website:

1. Launch an EC2 instance
2. Install a web server (Apache/Nginx)
3. Upload your website files
4. Access it via public IP

---

## Common Use Cases

* Hosting websites
* Running applications
* Testing software
* Machine learning workloads
* Game servers

---

## Advantages

* No need to buy hardware
* Scalable (increase/decrease resources anytime)
* Pay-as-you-go
* Full control over the server

---

## Disadvantages

* Requires basic server knowledge
* Can become costly if left running
* You are responsible for maintenance

---

## Pricing Basics

You pay for:

* Running time (per second/hour)
* Storage (EBS)
* Data transfer

---

## Types of Pricing

* **On-Demand** → Pay per use
* **Reserved Instances** → Cheaper for long-term
* **Spot Instances** → Very cheap but can stop anytime

---

## Summary

Amazon EC2 lets you run virtual computers in the cloud so you can build and host applications without buying physical machines.
