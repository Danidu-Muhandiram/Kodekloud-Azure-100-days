# Day 9: Attach Network Interface Card (NIC) to Azure Virtual Machine

### 🔐 Step 1: Log in to Azure Portal

- Open a browser
- Go to 👉 https://portal.azure.com
- Log in using credentials

---

### 🖥️ Step 2: Open the Virtual Machine

- In the top search bar, type:
  Virtual machines
- Click Virtual machines
- Select the VM:
  xfusion-vm (check details)

---

### ⚠️ Step 3: Ensure VM Initialization Is Completed

Before attaching a NIC:

- Check VM Status at the top
- It must be:
  - Running or Stopped
- ❌ Do NOT proceed if status is:
  - Provisioning
  - Starting
  - Updating

👉 If the VM is **Running**, you must stop it:

- Click **Stop**
- Wait until status becomes **Stopped**

*(Attaching a secondary NIC requires the VM to be stopped.)*

---

### 🌐 Step 4: Open Networking Settings

- Inside xfusion-vm
- From the left menu, click:
  Networking (linked title)
- Then click:
  Network Interface

---

### ➕ Step 5: Attach Existing Network Interface

- Click **Attach network interface**
- In the dropdown list, select:
  xfusion-nic (check details)
- Click **OK / Attach**

---

### 💾 Step 6: Save the Configuration

- Click **Save**
- Wait for the notification:
  **Update succeeded**

---

### ▶️ Step 7: Start the VM (If Stopped)

- Go back to **Overview**
- Click **Start**
- Wait until VM status becomes:
  **Running**

---

### ✅ Step 8: Verify NIC Status

## Method 1: From VM
- Go to **Networking**
- Confirm **xfusion-nic** is listed

## Method 2: From NIC
- Search for **Network interfaces**
- Open **xfusion-nic**
- Verify:
  - Status: **Attached**
  - Attached to: **xfusion-vm**
