# Deploy a website with Azure virtual machines
## 1. Introduction to Azure virtual machines
### 1.1 Compile a checklist for creating an Azure Virtual Machine
- Start with the network
- Name the VM
- Decide the location for the VM
- Determine the size of the VM
- Understanding the pricing model
- Storage for the VM
- Select an operating system
### 1.2 Exercise - Create a VM using the Azure portal
- Create an Azure VM with the Azure portal

The Azure portal provides an easy-to-use browser-based user interface that enables you to create and manage all your Azure resources.

- Configure the VM
### 1.3 Describe the options available to create and manage an Azure Virtual Machine
- Azure Resource Manager
- Azure PowerShell
- Azure CLI
- Programmatic (APIs)
- Azure VM extensions
- Azure Automation services
### 1.4 Manage the availability of your Azure VMs
- What is availability?
- Failover across locations
### 1.5 Back up your virtual machines

Azure Backup is a backup as a service offering that protects physical or virtual machines no matter where they reside: on-premises or in the cloud.

- Advantages of using Azure Backup
- Use Azure Backup
### 1.6 Knowledge check
1. Suppose you want to run a network appliance on a virtual machine. Which workload option should you choose?
  ```
  **Compute optimized**
  Compute optimized virtual machines are designed to have a high CPU-to-memory ratio. 
  Suitable for medium traffic web servers, network appliances, batch processes, and application servers.
  ```
2. True or false: Resource Manager templates are JSON files?
  ```
  **True**
  Resource Manager templates are JSON files that define the resources you need to deploy for your solution. 
  The template can then be used to easily re-create multiple versions of your infrastructure, such as staging and production.
  ```
## 2. Create a Linux virtual machine in Azure
## 3. Create a Windows virtual machine in Azure
## 4. Build and run a web application with the MEAN stack on an Azure Linux virtual machine
