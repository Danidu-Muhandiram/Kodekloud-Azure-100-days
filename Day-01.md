# KodeKloud Azure – Day 01  
## Solution: Creating an SSH Key in Azure

### Steps

1. Navigate to **https://portal.azure.com**
2. Log in using the provided credentials (email and password).
3. In the top search bar, search for **SSH keys**.
4. Click **+ Create**.
5. Select the existing **Resource Group**.
6. Copy the keyword from the instructions  
   *(e.g., `datacenter-kp`)* and paste it into **Key pair name**.
7. Set **SSH public key source** to **Generate new key pair**.
8. Set **SSH key type** to **RSA SSH Format**.
9. Click **Review + Create**.
10. After validation passes, click **Create**.
11. Click **Download private key and create resource**.
12. Refresh the page to confirm the SSH key is created successfully.

✅ SSH key creation completed.





<br>
<br>

# 🔐 PART 1 - What is Azure?



## 🔹 What is Microsoft Azure?
**Microsoft Azure** is a **cloud computing platform** provided by Microsoft.

Instead of buying and managing physical hardware, Azure allows you to **use computing resources over the internet**.

📌 Simply put:  
Azure lets you *rent* servers, storage, and networking when you need them.

---

## 🔄 Traditional vs Cloud Computing (Azure)

### 🏢 Traditional (On-Premises)
- Buy physical computers and servers
- Install operating systems manually
- Manage hardware, power, cooling, and maintenance
- High upfront cost
- Limited scalability


### ☁️ Cloud Computing (Azure)
- No need to buy physical servers
- Resources are available instantly
- Hardware is managed by Microsoft
- Pay only for what you use
- Easy to scale up or down

---

## 🧩 What Azure Provides

### 🖥️ 1. Compute
- **Virtual Machines (VMs)**
  - Linux or Windows servers
  - Used to run applications and services


### 💾 2. Storage
- Store files, backups, and databases
- Used for application data
- Highly scalable and reliable


### 🌐 3. Networking
- Virtual networks
- Load balancers
- Secure communication between resources


### 🔐 4. Security
- Identity and access management
- Network security
- Monitoring and compliance tools

---

## ⭐ Key Benefits of Azure
- 💰 **Cost-effective** - Pay only for what you use
- 📈 **Scalable** - Increase or decrease resources anytime
- 🌍 **Reliable** - Global data centers with high availability
- 🔒 **Secure** - Built-in security and compliance features

---

## 🧪 Simple Real-World Example
Instead of buying a physical server to host a website:

1. Create a **Virtual Machine** in Azure  
2. Deploy your website  
3. Pay only for the time and resources you use  


<br>

# 🔐 PART 2 - What is SSH?

### 🔑 SSH (Secure Shell)
**SSH** is a secure method used to **connect to and control remote servers**, mainly **Linux servers**, over the internet.

You can think of SSH as a **safe tunnel** between your computer and a server.

---

### 🌐 What SSH Is Commonly Used For
- Logging into a remote Linux server
- Running commands on a server
- Managing cloud servers (like Azure Virtual Machines)
- Securely copying files

---

### ❌ Without SSH (Not Secure)
If a connection is not secured:
- Data is sent as **plain text**
- Anyone on the network could **read the data**
- Passwords could be **stolen**
- Older tools like **Telnet** had this problem

---

### ✅ With SSH (Secure)
SSH protects your connection by:
- Encrypting all data
- Hiding commands and passwords
- Making sure you are connecting to the **correct server**

This protects against:
- Eavesdropping
- Data tampering
- Fake servers

---

### 🔐 How SSH Login Works (Simple)
SSH supports two main ways to log in:
- **Password authentication** (easy, less secure)
- **SSH key authentication** (recommended)

📌 SSH keys work using a **key pair**:
- **Private key** → stays on your computer (keep it secret)
- **Public key** → stored on the server

---

### ☁️ SSH in Azure (Why It Matters)
- SSH is the **default way** to connect to Linux Azure VMs
- Azure encourages **SSH key login** instead of passwords
- This greatly improves server security

---





