# Day 4: Create a Virtual Network (VNet) in Azure

### Step 1: Login to Azure Portal
- Open: https://portal.azure.com
- Login using your provided credentials

---

### Step 2: Open Virtual Network Creation
- Use the **top search bar**
- Search for **Virtual Network**
- Click **Create**

---

### Step 3: Basics Tab
Fill the following details:

- **Subscription:** Leave default  
- **Resource group:** Select the existing resource group (**very important**)  
- **Name:** `xfusion-vnet`  
- **Region:** `East US`

Click **Next: IP Addresses**

---

### Step 4: IP Addresses Tab
- **Address space:**  
10.0.0.0/16

(This is the default, but verify it)

- Keep the **default subnet** (Azure creates it automatically)

Click **Review + Create**

---

### Step 5: Create the VNet
- Click **Create**
- Wait until you see **Deployment succeeded** 🎉

---

### Step 6: Verify Using Azure CLI
Run the following command:

```bash
az network vnet list -o table
```


### Verification Check

If you see xfusion-vnet in the list, the task is completed successfully ✅


<br>
<br>


# Azure Virtual Network (VNet)

## What is a Virtual Network (VNet)?

A **Virtual Network (VNet)** is a **private network inside Microsoft Azure**.

It is similar to:
- A home Wi-Fi network
- A company’s internal LAN network

Resources inside a VNet can communicate **securely with each other**, but are **isolated from the public internet by default**.

---

## Why Do We Need a VNet?

Azure resources such as:
- Virtual Machines (VMs)
- Databases
- Web Applications

**must live inside a network** to communicate.

A VNet allows you to:
- Control **IP addressing**
- Define **network boundaries**
- Secure communication between resources
- Connect Azure resources to on-premises networks

---

## VNet as a Foundation Layer

Think of Azure infrastructure in layers:

1. **Virtual Network (VNet)** → Network foundation  
2. **Subnet** → Smaller network inside VNet  
3. **Resources** → VM, database, app, etc.

Without a VNet:
- You cannot properly deploy or manage most Azure resources

---

## Address Space (CIDR Block)

When creating a VNet, you define an **address space**.

Example:10.0.0.0/16


This means:
- All resources inside the VNet get **private IP addresses**
- These IPs are **not accessible from the internet directly**

### Why CIDR is Important
- Prevents IP conflicts
- Helps in network planning
- Enables future expansion

---

## Subnets (Inside a VNet)

A **Subnet** is a **smaller network inside a VNet**.

Example:
- VNet: `10.0.0.0/16`
- Subnet: `10.0.1.0/24`

Why subnets matter:
- Separate workloads (frontend, backend, database)
- Apply different security rules
- Improve network organization

Azure creates a **default subnet automatically** if you don’t specify one.

---

## Region and VNet

A VNet is always created in **one Azure region**.

Example:
- Region: `East US`

Important points:
- A VNet **cannot span multiple regions**
- Resources inside the VNet must be in the **same region**

---

## Security and Isolation

A VNet provides:
- **Network isolation** from other VNets
- Controlled access using:
  - Network Security Groups (NSGs)
  - Route tables
  - Firewalls

By default:
- Resources inside a VNet can communicate with each other
- Internet access is **restricted unless allowed**

---

## Communication Options with VNet

A VNet can communicate with:
- Other VNets (VNet Peering)
- On-premises networks (VPN / ExpressRoute)
- Internet (with proper rules)

This makes VNets suitable for:
- Hybrid cloud setups
- Enterprise networks
- Secure internal systems

---

## Real-World Use Case Example

In a DevOps migration project:
- Step 1: Create VNet
- Step 2: Create subnets
- Step 3: Deploy VMs into subnets
- Step 4: Apply security rules
- Step 5: Connect to on-prem network

This **incremental approach** reduces risk and downtime.

---

## Key Takeaways

- VNet is the **core networking component** in Azure
- It provides **private, secure communication**
- CIDR blocks define IP ranges
- Subnets organize resources
- VNets are region-specific
- Essential for real-world cloud architecture

