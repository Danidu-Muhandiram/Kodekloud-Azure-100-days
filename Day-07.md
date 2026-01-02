# Day 7: Create a Public IP Address for Azure VM

# 🔐 Step 1: Log in to Azure Portal

- Open your browser
- Go to 👉 https://portal.azure.com
- Log in using the provided username and password

---

# 🌐 Step 2: Open Public IP Address Service

- In the top search bar, type:
  Public IP addresses
- Click Public IP addresses from the results.

---

# ➕ Step 3: Create a New Public IP

- Click + Create

---

# ⚙️ Step 4: Configure Basics

## Project details
- Subscription: Leave default
- Resource group:
  - Select an existing one

## Instance details
- Name: xfusion-pip (check details)
- Region: Choose the default
- IP Version: IPv4
- IP assignment: Static (default)
- SKU: Basic (standard)

---

# 🔍 Step 5: Review + Create

- Click Review + create
- Wait for validation to pass
- Click Create

---

# ✅ Step 6: Verify Creation

- Once deployment completes, click Go to resource
- Confirm:
  - Name: xfusion-pip
  - Status: Provisioned
  - IP address is visible
