
# Azure Policy: Restricted Resource Creation and VM Configuration

---

This Azure Policy enforces strict control over resource deployments within its assigned scope by implementing a "deny by default" approach. It permits the creation of only essential resource types and mandates specific configurations for Linux Virtual Machines.

## Key Restrictions & Allowances

* **Allowed Resource Types:**
    * **Resource Groups** (`Microsoft.Resources/resourceGroups`)
    * **Virtual Networks** (`Microsoft.Network/virtualNetworks`)
    * **Subnets** (`Microsoft.Network/virtualNetworks/subnets`)
    * **Public IP Addresses** (`Microsoft.Network/publicIPAddresses`)
    * **Network Interfaces** (`Microsoft.Network/networkInterfaces`)
    * **Network Security Groups** (`Microsoft.Network/networkSecurityGroups`)
    * **Route Tables** (`Microsoft.Network/routeTables`)
    * **Virtual Network Gateways** (`Microsoft.Network/virtualNetworkGateways`)
    * **Virtual Network Connections** (`Microsoft.Network/connections`)
    * **Managed Disks** (for VMs) (`Microsoft.Compute/disks`)
* **Virtual Machine (VM) Specifics:**
    * Only **Linux Virtual Machines** are permitted.
    * VM creation is restricted to the **East US** Azure region.
    * Allowed VM sizes are limited to **Standard\_B2ms** and **Standard\_B2s**.

Any attempt to deploy a resource type not explicitly listed above, or a Linux VM that doesn't meet the specified region or size criteria, will be denied by this policy.