# 🌐 Day 5: Create a Virtual Network (IPv4) in Azure

### 🔐 Step 1: Login to Azure Portal

1. Open your web browser
2. Go to: https://portal.azure.com
3. Login using the **Azure credentials**

---

### 🔍 Step 2: Open Virtual Network Service

1. In the **top search bar**, type **Virtual Network**
2. Click **Virtual networks**
3. Click **+ Create**

---

### ⚙️ Step 3: Basics Tab

### 🔹 Project Details
- **Subscription**: Leave default
- **Resource group**:  
  Select the **existing resource group**  
  ⚠️ Do **NOT** create a new resource group

### 🔹 Instance Details
- **Name**: `xfusion-vnet`(check your details)
- **Region**: `East US`

Click **Next (IP Addresses)**

---

### 🌐 Step 4: IP Addresses Tab

### 🔹 IPv4 Address Space
1. Remove the default address range (if present)
2. Add the following IPv4 CIDR:

192.168.0.0/24

### 📘 What does `/24` mean?
- Allows **256 private IP addresses**
- Commonly used for **small to medium networks**

### 🔹 Subnet
- Azure automatically creates a default subnet
- You can leave it unchanged for now

Click **Next** until you reach **Review + Create**

---

### ✅ Step 5: Review + Create

1. Azure validates your configuration
2. If validation passes, click **Create**

⏳ Deployment usually takes **30–60 seconds**

---

### 🎉 Step 6: Verify the Virtual Network

1. Go to **Virtual Networks**
2. Confirm **xfusion-vnet** is listed
3. Click the VNet and verify:
   - **Region** → East US
   - **Address space** → `192.168.0.0/24`

<br>
<br>

## 1️⃣ What is an Azure Virtual Network (VNet)?

An **Azure Virtual Network (VNet)** is a **logically isolated private network** in the Azure cloud.

It enables:
- Secure communication between Azure resources
- Network isolation between environments
- Control over IP addressing and traffic flow

A VNet is similar to a **traditional on-premises LAN**, but:
- It is software-defined
- Fully managed by Azure
- Highly scalable and secure

---

## 2️⃣ Why IPv4 is Used in Azure VNets

Azure VNets support:
- **IPv4**
- **IPv6** (optional, advanced)

Most environments use **IPv4** because:
- Widely supported
- Simple to understand
- Compatible with most applications and services

In this guide, we focus on **IPv4-only VNets**.

---

## 3️⃣ Understanding IPv4 Addressing in VNets

### 🔹 What is an IPv4 Address?
An IPv4 address:
- Is a 32-bit number
- Written in dotted decimal format
- Example: 192.168.0.1

### 🔹 Private IP Ranges Used in Azure
Azure VNets use **private IP ranges** defined by RFC 1918:

| Range | Usage |
|------|------|
| 10.0.0.0/8 | Large networks |
| 172.16.0.0/12 | Medium networks |
| 192.168.0.0/16 | Small networks |

Example used in this project: 192.168.0.0/24

---

## 4️⃣ CIDR Notation Explained (`/24`)

CIDR (Classless Inter-Domain Routing) defines **network size**.

### Example: 192.168.0.0/24

### Meaning:
- `/24` → First 24 bits are network bits
- Remaining 8 bits are host bits
- Total addresses: **256**
- Usable addresses: **251** (Azure reserves 5)

### Azure Reserved IPs (Important)
Azure always reserves:
1. Network address
2. Default gateway
3. Azure DNS
4. Azure services
5. Broadcast address

---

## 5️⃣ Address Space vs Subnet (Critical Concept)

### 🔹 Address Space
- Defines the **entire IP range** of the VNet
- Example: 192.168.0.0/24

### 🔹 Subnet
- A **smaller IP range inside the VNet**
- Used to organize resources

Example:
VNet: 192.168.0.0/24
Subnet1: 192.168.0.0/26
Subnet2: 192.168.0.64/26


📌 **Rule**: Subnets must always fit **inside** the VNet address space.

---

## 6️⃣ Why Subnets Are Important

Subnets allow:
- Logical separation of workloads
- Applying security rules (NSGs)
- Traffic control and routing
- Better scalability and management

Typical subnet usage:
- Web subnet
- App subnet
- Database subnet
- Management subnet

---

## 7️⃣ How Traffic Flows Inside a VNet

By default:
- All resources inside a VNet can communicate
- All subnets can talk to each other
- Traffic is **private and isolated**

Azure handles:
- Routing
- IP assignment
- DNS resolution

No manual routing is required initially.

---

## 8️⃣ VNet Isolation and Security

Each VNet is:
- Isolated from other VNets by default
- Isolated from on-prem networks unless connected

Security can be enforced using:
- Network Security Groups (NSGs)
- Azure Firewall
- Route Tables

---

## 9️⃣ VNet Peering (Concept Overview)

**VNet Peering** allows:
- Two VNets to communicate privately
- Traffic to stay on Azure’s backbone network

Common use cases:
- Dev ↔ Test ↔ Prod communication
- Shared services VNet
- Hub-and-spoke architecture

---

## 🔟 Region Scope of VNets

A VNet:
- Belongs to **one Azure region**
- Cannot span multiple regions

However:
- VNets in different regions can be peered
- Enables global architectures

Example:
East US VNet ↔ West Europe VNet

---

## 1️⃣1️⃣ Common IPv4 Design Mistakes (Avoid These)

❌ Overlapping CIDR ranges  
❌ Very small address spaces  
❌ No future growth planning  
❌ Mixing public IPs inside VNets  
❌ Poor subnet segmentation  

✔ Always plan for expansion

---

## 1️⃣2️⃣ Best Practices for IPv4 VNets

✔ Use non-overlapping CIDR blocks  
✔ Allocate more IPs than needed  
✔ Separate workloads using subnets  
✔ Keep one VNet per environment  
✔ Document IP ranges clearly  

---

## 1️⃣3️⃣ Real-World Example

### Scenario:
A small application environment

VNet: 192.168.0.0/24

Subnets:

Web: 192.168.0.0/26

App: 192.168.0.64/26

Database: 192.168.0.128/26

✔ Secure  
✔ Scalable  
✔ Clean design  

---

## 1️⃣4️⃣ Summary

- Azure VNet is the foundation of networking
- IPv4 addressing defines communication boundaries
- CIDR planning is critical for scalability
- Subnets control structure and security
- Good design prevents future rework
