# Day 10: Attach Public IP to Azure Virtual Machine

### 🔐 Step 1: Log in to Azure Portal

- Open a browser
- Go to 👉 https://portal.azure.com
- Log in with credentials

---

### 🖥️ Step 2: Open the Virtual Machine

- In the top search bar, type:
  Virtual machines
- Click **Virtual machines**
- Select the VM named:
  devops-vm-pip (check details)

---

### 🌐 Step 3: Go to the VM’s Network Interface

- Inside the VM page, click:
  **Network Settings** (left menu)
- Under **Network interface**, click the NIC name  
  *(usually looks like: devops-vm-pip-nic)*

👉 This opens the **Network Interface** resource

---

### 🔗 Step 4: Attach the Public IP to the NIC

- In the NIC page, click:
  **IP configurations** (left menu)
- Click the IP configuration  
  *(usually named: ipconfig1)*
- Under **Public IP address**, click the dropdown
- Select:
  devops-pip (check)
- Click **Save**

⏳ Wait a few seconds for Azure to apply the change

---

### ✅ Step 5: Verify Public IP Is Assigned

## Method 1: From NIC
- Stay in **IP configurations**
- Confirm:
  **Public IP: devops-pip**

## Method 2: From VM
- Go back to **Virtual machines**
- Open **devops-vm-pip**
- Open **Networking**
- Confirm a **Public IP address** is displayed
