
##  Develop Azure Infrastructure as a Service compute solution 



### Azure Virtual Machines


Virtual machines are part of the Infrastructure as a Service (IaaS) offering. Azure Virtual Machines (VM) is one of several types of on-demand, scalable computing resources that Azure offers. Typically, you choose a VM when you need more control over the computing environment than the other choices offer.


VM requires setup
- Network - 
- Naming of VM. Recomended to user standard so name reflect what VM is doing. Environment, location, instance, product and service
- Location of VM. There ere serveral Regions for Azure. [See overview here](https://azure.microsoft.com/en-us/global-infrastructure/regions/). See list [here](https://azure.microsoft.com/en-us/global-infrastructure/locations/)


### Size of VM

Microsoft have different types of sizes available for Virtual Machines. 


### General purpose
Balanced CPU-to-memory ratio. Ideal for testing and development, small to medium databases, and low to medium traffic web servers.

### Compute optimized
High CPU-to-memory ratio. Good for medium traffic web servers, network appliances, batch processes, and application servers.

### Memory optimized
High memory-to-CPU ratio. Great for relational database servers, medium to large caches, and in-memory analytics.

### Storage optimized
High disk throughput and IO ideal for Big Data, SQL, NoSQL databases, data warehousing and large transactional databases.

### GPU
Specialized virtual machines targeted for heavy graphic rendering and video editing, as well as model training and inferencing (ND) with deep learning. Available with single or multiple GPUs.

### High performance compute
Our fastest and most powerful CPU virtual machines with optional high-throughput network interfaces (RDMA).


See list for [Windows VM](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes) and [Linux VM](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/sizes)


## Pricing model

The cost for Virtual Machines are combined of
- Compute Costs
Compute expenses are priced on a per-hour basis but billed on a per-minute basis.
- Storage cost
You are charged separately for the storage the VM uses



## Storage for VM

All Azure virtual machines will have at least two virtual hard disks (VHDs).

## Operating systems
Azure provides many marketplace images to use with various versions and types of Windows Server operating systems. Marketplace images are identified by image publisher, offer, sku, and version (typically version is specified as latest).



## Options to create Azure Virtual Machines

### Azure Portal
VMs can be created for portal

### Azure Resource Manager


#### Resource Manages Templates
JSON file with configuration info

TODO add more

#### Azure Powershell

#### Azure CLI


#### Programmatic (APIs)

##### Azure REst API

#### Azure Client SDK


## Azure VM Extensions



## Avaiability
### Availability set

An availability set is a logical feature used to ensure that a group of related VMs are deployed so that they aren't all subject to a single point of failure and not all upgraded at the same time during a host operating system upgrade in the datacenter.


### Fault domain
A fault domain is a logical group of hardware in Azure that shares a common power source and network switch

### Update domain



## Train

### Setup image portal


### Setpu image Powershell


### Cloudshell



## Resource Manager

