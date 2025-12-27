# Day 3: Create VM using Azure CLI 🚀

Azure Virtual Machine (VM) directly from the terminal using the Azure CLI.

### 1. Check for Existing Resource Groups

Before creating a VM, ensure you have a valid Resource Group. This command lists all groups available to your subscription in a readable table format.

```bash
az group list -o table

```

### 2. Create the Virtual Machine

Run the following command to create the VM. This command uses the `Ubuntu2204` image and automatically generates SSH keys if they do not already exist on your local machine.

```bash
az vm create \
  --resource-group kml_rg_main-a4c6ff4a4b54426b \
  --name xfusion-vm \
  --image Ubuntu2204 \
  --size Standard_B2s \
  --admin-username azureuser \
  --generate-ssh-keys \
  --storage-sku Standard_LRS \
  --os-disk-size-gb 30 \
  --output table

```

### 3. Command Breakdown

Here is a detailed explanation of the flags used in the creation command:

| Option | Description |
| --- | --- |
| `--resource-group` | The logical container where the VM and its resources are deployed. |
| `--name` | The unique identifier for the Virtual Machine (e.g., `xfusion-vm`). |
| `--image` | The Operating System image to install (e.g., `Ubuntu2204`). |
| `--size` | The VM size (CPU/RAM). `Standard_B2s` is a burstable, general-purpose size. |
| `--admin-username` | The username used to SSH into the machine (`azureuser`). |
| `--generate-ssh-keys` | Checks for existing keys in `~/.ssh`; creates new ones if missing. |
| `--storage-sku` | The redundancy/performance tier of the disk (`Standard_LRS` is standard locally redundant storage). |
| `--os-disk-size-gb` | The size of the Operating System disk in Gigabytes (`30`). |
| `--output table` | Formats the JSON output into a clean, human-readable ASCII table. |

### 4. Verify VM Status

```bash
az vm get-instance-view \
  --resource-group kml_rg_main-a4c6ff4a4b54426b \
  --name xfusion-vm \
  --query instanceView.statuses[1] \
  --output table

```

**Expected Output:**
If the provisioning was successful, you should see the `PowerState` listed as running.

```text
Code                DisplayStatus
------------------  ---------------
PowerState/running  VM running

```

<BR>
<BR>




# 🌐 Azure CLI
<BR>



### 1️⃣ What is a Virtual Machine (VM)?
- A VM is a **computer inside the cloud**.
- It behaves like a physical computer:
  - CPU
  - RAM
  - Disk
  - Operating System
- You can run programs, install software, and connect remotely.
- Azure VMs are Microsoft’s cloud-hosted computers.

**Analogy:** Renting a remote PC you can access from anywhere.

---

### 2️⃣ Resource Group
- Think of it as a **folder in Azure**.
- Organizes all resources (VMs, storage, networking) together.
- Helps manage and delete resources easily.

---

### 3️⃣ OS Image
- Image = Operating System **pre-installed on the VM**.
- Examples:
  - Ubuntu 22.04 LTS (Linux)
  - Windows Server
- Azure provides ready-made images, so no manual OS installation is required.

---

### 4️⃣ VM Size
- Determines performance:
  - CPU cores
  - RAM
  - Temporary disk
- Example:
  - `Standard_B1s` or `Standard_B2s`
  - Small, cheap, suitable for practice or lightweight tasks.

---

### 5️⃣ Networking & NSG (Firewall)
- Each VM has a network interface.
- NSG (Network Security Group) acts like a **firewall**.
- Controls which ports are open.
- For Linux SSH access, **port 22 must be open**.

---

### 6️⃣ SSH (Secure Shell)
- Secure way to connect to Linux VMs remotely.
- Uses **SSH keys (public & private)** instead of passwords.
- `.pem` file = private key used to prove your identity.

**Conceptual Flow:**
1. VM stores the **public key**
2. You connect using the **private key**
3. SSH verifies both → access granted

---

### 7️⃣ Storage & Disks
- VM needs a disk to store OS and files.
- Disk types:
  - Standard HDD → slower, cheap
  - Standard SSD → faster, more expensive
- OS Disk = main drive where the OS lives.
- Cloud Shell also uses storage (Azure File Share) to persist uploaded files temporarily.

---

### 8️⃣ Why “Incremental Migration” in DevOps
- Companies move to the cloud **gradually**, not all at once.
- Step-by-step VM creation helps learn safe cloud deployment and infrastructure management.


