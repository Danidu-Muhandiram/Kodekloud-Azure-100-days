### Day 2: Create an Azure Virtual Machine

### 1️⃣ Step 1: Start Creating the VM
1. In the top search bar, type:  
   `Virtual machines`
2. Click **Virtual machines**.
3. Click **+ Create**.
4. Choose **Virtual machine**.


### ⚙️ Step 2: Basics Tab (MOST IMPORTANT)

### 1. Resource Group
- Select the **existing resource group**.  
- ❌ **Do NOT create a new one**.  
> Resource group = container already prepared for you

### 2. Virtual Machine Name
- Enter exactly: according to instructions

### 3. Region
- Select: **West US**  
> Region = physical data center location

### 4. Image (Operating System)
- Click **Image** dropdown.  
- Choose: **Ubuntu Server 22.04 LTS - x64 Gen2**  
> This is your Linux OS

### 5. VM Size
- Click **See all sizes**.  
- Search or scroll, then select: **Standard_B1s**  
> Small, cheap VM – perfect for practice  
- Click **Select**

### 6. Authentication Type
- Choose: **SSH public key** (default selected)  
- Then:
  - SSH public key source → **Generate new key pair**
  - Key pair name → any name (e.g., `xfusion-key`)  
✅ Leave everything else as default  

- Click **Next: Disks**

### 💾 Step 3: Disks Tab
1. **OS Disk size** → `30 GB`
2. **OS Disk type** → `Standard HDD`  
> HDD = slower but cheaper (required by task)  

✅ Leave everything else default  

- Click **Next: Networking**  

✅ Do NOT change anything else

### ✅ Step 4: Review & Create
- Azure validates your settings.  
- If validation passes → Click **Create**  
- Download the SSH private key (`.pem`) when prompted.  
> Save it safely!  

⏳ Deployment takes ~30–60 seconds.

<br>
<br>

---

## 1️⃣ What is a Virtual Machine (VM)?
- A VM is a **computer inside the cloud**.  
- Behaves like a physical computer: has **CPU, RAM, disk, and an operating system**.  
- You can **run programs, install software, and connect remotely**.  
- **Azure VMs** are Microsoft’s cloud-hosted computers.  

**Analogy:** Renting a remote PC you can access from anywhere.

---

## 2️⃣ Resource Group
- Think of it as a **folder in Azure**.  
- Organizes all resources (VMs, storage, networking) together.  
- Helps **manage and delete resources easily**.

---

## 3️⃣ OS Image
- Image = Operating System **pre-installed on the VM**.  
- Example: `Ubuntu 22.04 LTS` (Linux) or `Windows Server`.  
- Azure provides ready-made images → no need to install OS manually.

---

## 4️⃣ VM Size
- Determines **performance**:
  - CPU cores  
  - RAM  
  - Temporary disk  
- Example: `Standard_B1s` = small, cheap, suitable for practice or lightweight tasks.

---

## 5️⃣ Networking & NSG (Firewall)
- Each VM has a **network interface**.  
- **NSG (Network Security Group)** → like a firewall.  
- Controls which **ports are open**.  
- For Linux SSH: **port 22 must be open**.

---

## 6️⃣ SSH (Secure Shell)
- Secure way to connect to **Linux VMs remotely**.  
- Uses **SSH keys (public/private)** instead of passwords.  
- `.pem` file = private key used to prove your identity.  

**Conceptual flow:**
1. VM stores a **public key**.  
2. You connect using your **private key**.  
3. SSH verifies keys → grants access.

---

## 7️⃣ Storage & Disks
- VM needs a **disk to store OS and files**.  
- Types:
  - **Standard HDD** → slower, cheap  
  - **Standard SSD** → faster, more expensive  
- **OS Disk** = main drive where the OS lives.  
- Cloud Shell also needs storage (Azure File Share) to **persist uploaded files temporarily**.

---

## 8️⃣ Why “Incremental Migration” in DevOps
- In real scenarios, companies **move gradually to the cloud**.  
- Step-by-step VM creation teaches **safe deployment and cloud infrastructure management**.
