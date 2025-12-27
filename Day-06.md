# Day 6: Create a Subnet in Azure Virtual Network

## Step 1: Log in to Azure Portal
- Open your browser and go to: [https://portal.azure.com](https://portal.azure.com)
- Log in using your Azure credentials (you can retrieve them using `showcreds` on the azure-client host if needed).

---

## Step 2: Search for Virtual Networks
- In the top search bar, type: **Virtual Networks**  
- Click **Virtual networks** from the results.  

---

## Step 3: Create a New VNet
- Click **+ Create → + Virtual network**  
- You will see the **Basics** tab.

### Fill in the fields:

| Field             | Value            | Explanation                                             |
|------------------|----------------|--------------------------------------------------------|
| Subscription      | Select your subscription (default) | The subscription under which this VNet will be created |
| Resource Group    | Select existing | Resource Groups are like folders to organize resources |
| Name              | `xfusion-vnet`  | This is your VNet name (check your details)                                 |
| Region            | East US         | Choose the Azure region closest to your users or team  (check your details) |
| IPv4 Address Space | `10.0.0.0/16`  | Defines the network range for your VNet (can host 65,536 addresses) |

> ⚡ **Tip:** `/16` is big enough for many subnets; each subnet will get its own smaller range.

---

## Step 4: Create a Subnet
- In the same **Create VNet** page, go to the **IP Addresses** tab.  
- Click **+ Add subnet**  

### Fill in the subnet fields:

| Field              | Value            | Explanation                                   |
|-------------------|----------------|-----------------------------------------------|
| Subnet name        | `xfusion-subnet` | Add your subnet name according to details given                |
| Subnet address range | `10.0.0.0/24`  | Subnet is a smaller network within the VNet (256 addresses) |

- Click **Add** to add the subnet.  

> ⚡ **Note:** The `/24` subnet range is a common choice for small deployments.

---

## Step 5: Review and Create
- Click the **Review + Create** tab  
- Verify all details:  
  - Name: `xfusion-vnet` (your name) 
  - Region: East US  (your region)
  - Address Space: `10.0.0.0/16`  
  - Subnet: `xfusion-subnet → 10.0.0.0/24`  
- Click **Create**  

Azure will deploy the VNet and subnet. It usually takes a few seconds to a minute.

---

## Step 6: Verify Your VNet
- Go back to **Virtual Networks** in the portal.  
- Click on `xfusion-vnet`  
- Check:  
  - **Overview:** Region, Address space, Subnets  
  - **Subnets tab:** `xfusion-subnet` with `10.0.0.0/24`  

✅ **You’ve successfully created a VNet and a subnet!**

<br>
<br>

### Azure Virtual Network (VNet) and Subnets (IPv4)

### 1. Introduction to Azure VNet
Azure Virtual Network (VNet) is the **fundamental building block for private networking in Azure**. It allows you to:

- Isolate resources from the public internet
- Connect Azure resources securely
- Control IP address ranges, subnets, and routing
- Connect to on-premises networks via VPN or ExpressRoute

Think of a **VNet as your private network in Azure**, similar to a corporate LAN in an office.

---

### 2. IPv4 Addressing in VNet

### VNet Address Space
- Every VNet requires an **IPv4 address space**, written in **CIDR notation**.
- Example: `10.0.0.0/16`
  - `/16` indicates the **subnet mask** and number of addresses.
  - `/16` = **65,536 IP addresses** (`10.0.0.0` → `10.0.255.255`).

> ⚡ **Tip:** Choose private IP ranges:  
> - `10.0.0.0/8` → 16M addresses  
> - `172.16.0.0/12` → 1M addresses  
> - `192.168.0.0/16` → 65k addresses  

### Example VNet CIDR
| VNet Name       | Address Space | Total IPs    |
|----------------|---------------|-------------|
| xfusion-vnet   | 10.0.0.0/16   | 65,536     |

---

### 3. Subnets in Azure VNet
Subnets are **smaller divisions within a VNet**, used to group resources logically.

### Key Points
- Each subnet must be **within the VNet address space**
- Subnets divide the network for isolation and management
- Azure reserves 5 IP addresses per subnet for internal use  
  - Example: first subnet `10.0.0.0/24` → usable IPs = `10.0.0.4` → `10.0.0.254`

### Common Subnet Sizes (CIDR)
| CIDR | IP Addresses | Usable IPs |
|------|-------------|------------|
| /24  | 256         | 251        |
| /25  | 128         | 123        |
| /26  | 64          | 59         |

### Example
VNet: 10.0.0.0/16
Subnet 1: 10.0.0.0/24 (xfusion-subnet)
Subnet 2: 10.0.1.0/24 (backend-subnet)
Subnet 3: 10.0.2.0/24 (dmz-subnet)

- Each subnet can host different types of resources (Web servers, DB servers, etc.)

---

### 4. VNet-to-Subnet Relationship
VNet (10.0.0.0/16)
├── Subnet 1: 10.0.0.0/24 (Web)
├── Subnet 2: 10.0.1.0/24 (DB)
└── Subnet 3: 10.0.2.0/24 (App)


- **VNet = entire network (like a building)**
- **Subnet = sections/rooms inside the building**

---

### 5. Best Practices for VNet and Subnets
1. **Plan Addressing in Advance**
   - Avoid overlapping IP ranges
   - Keep future expansion in mind
2. **Use Logical Subnets**
   - Group resources by function (Web, App, DB)
3. **Use Private IP Ranges**
   - Avoid public IPs for internal resources
4. **Reserve Enough IPs per Subnet**
   - Consider growth, scaling, and Azure reserved IPs
5. **Use Network Security Groups (NSGs)**
   - Control traffic flow at subnet level

---

### 6. Azure VNet Components
- **Subnets** – smaller networks in VNet  
- **Network Security Groups (NSGs)** – firewall rules for subnets  
- **Route Tables** – define traffic routing  
- **Peering** – connect VNets securely  
- **Gateways** – connect to on-premises networks

---

### 7. Summary
- **VNet** = Private network in Azure (`10.0.0.0/16`)  
- **Subnet** = Smaller network inside VNet (`10.0.0.0/24`)  
- **CIDR** notation defines number of addresses  
- **Best Practices**: plan, use private ranges, group resources, and secure subnets
