# Day 11: Change Azure Virtual Machine Size Using Console

### 🔐 Step 1: Log in to Azure Portal

- Open your browser
- Go to 👉 https://portal.azure.com
- Log in using credentials

---

### 🖥️ Step 2: Open the Virtual Machine

- In the top search bar, type:
  Virtual machines
- Click **Virtual machines**
- Select the VM named:
  datacenter-vm (check details)

---

### 🔄 Step 3: Stop the VM (Required for Resize)

Azure requires the VM to be stopped (deallocated) before resizing.

- Inside **datacenter-vm**
- Click **Stop**
- Wait until:
  **Status = Stopped (deallocated)**

---

### 📏 Step 4: Change the VM Size

- In the bottom menu, click **Size**
- In the list:
  - Select: **Standard_B2s**
- Click **Resize**
- Wait for the resize operation to complete

✅ You should see a success notification

---

### ▶️ Step 5: Start the VM Again

- Go back to **Overview**
- Click **Start**
- Wait until:
  **Status = Running**

---

### ✅ Step 6: Final Verification (Very Important)

In **Overview**, confirm:

✔ Size: **Standard_B2s**  
✔ Status: **Running**  

If all are correct → task completed successfully 🎯
