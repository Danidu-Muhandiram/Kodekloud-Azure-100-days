# Day 8: Attach Managed Disk to Azure Virtual Machine

### 🔐 Step 1: Login to Azure Portal

- Open browser
- Go to 👉 https://portal.azure.com
- Login using details

---

### 🖥️ Step 2: Open the Virtual Machine

- In the top search bar, type:
  Virtual machines
- Click Virtual machines
- Select the VM named:
  datacenter-vm

---

### ⚠️ Step 3: Ensure VM Initialization Is Complete

Before attaching the disk:

- Check VM Status at the top
- It should be **Running** or **Stopped**
- ❌ Do NOT attach while VM is provisioning
- If it shows **Starting / Updating**, wait until it finishes

---

### 💽 Step 4: Open Disks Section

- Inside datacenter-vm
- From the left menu, click:
  Disks (Seach "Disks")

---

### ➕ Step 5: Attach Existing Data Disk

- Under **Data disks** section
- Click **+ Add existing data disk**
- In the new row:
  - Name → select: (according to details given)
    datacenter-disk
  - Disk type → leave default
  - Host caching → None (recommended for data disks)

---

### 💾 Step 6: Save Configuration

- Click **Apply** at the bottom
- Wait until the update completes
- ✔ You’ll see a notification:
  “Update succeeded”

---

### ✅ Step 7: Verify Disk Attachment

- Stay on **Disks** page
- Confirm:
  - datacenter-disk appears under **Data disks**
