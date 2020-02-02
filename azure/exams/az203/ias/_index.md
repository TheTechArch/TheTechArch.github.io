
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

```bash
az vm create --resource-group TutorialResources \
  --name TutorialVM1 \
  --image UbuntuLTS \
  --generate-ssh-keys \
  --output json \
  --verbose 
```


```bash

#!/bin/bash

# Replace the following URL with a public GitHub repo URL
gitrepo=https://github.com/Azure-Samples/php-docs-hello-world
webappname=mywebapp$RANDOM

# Create a resource group.
az group create --location westeurope --name myResourceGroup

# Create an App Service plan in `FREE` tier.
az appservice plan create --name $webappname --resource-group myResourceGroup --sku FREE

# Create a web app.
az webapp create --name $webappname --resource-group myResourceGroup --plan $webappname

# Deploy code from a public GitHub repository. 
az webapp deployment source config --name $webappname --resource-group myResourceGroup \
--repo-url $gitrepo --branch master --manual-integration

# Copy the result of the following command into a browser to see the web app.
echo http://$webappname.azurewebsites.net

```


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



### Documentation
[Full documentation for Azure CLI you find here](https://docs.microsoft.com/nb-no/cli/azure/?view=azure-cli-latest)



## Encryption
### Storage Service Encrypt
Default. Managed services


## Azure Disk Encryption

Bitlocker



## Azure Batch
Large-scale paralell and hig performance computing



Azure Batch creates and manages a pool of compute nodes

Batch can be controlled through Batch APIs and tools, command-line scripts, or the Azure portal to configure, manage, and monitor batch jobs.


Azure Batch can be used for Intrinsically parallel jobs, where the nodes does not need to talk to each other or you can run your tightly coupled workloads with Batch using Microsoft MPI or Intel MPI
to talk to each other.


### Azure Batch Service REST API

Azure Batch REST APIs can be accessed from within a service running in Azure, or directly over the Internet from any application that can send an HTTPS request and HTTPS response.

All access to the Batch service requires a Batch account, and the account is the basis for authentication. The Base URL for Batch service is https://{account-name}.{region-id}.batch.azure.com.




### Azure Batch service resources

#### Account
A Batch account is a uniquely identified entity within the Batch service. All processing is associated with a Batch account.

#### Azure Storage account
Most Batch solutions use Azure Storage for storing resource files and output file

#### Compute node
A compute node is an Azure virtual machine (VM) or cloud service VM that is dedicated to processing a portion of your application's workload. 

#### Pool
A pool is a collection of nodes that your application runs on.

#### Compute nodes
When you create a pool, you can specify which types of compute nodes you want and the target number for each. Dedicated compute nodes or 
Low-priority compute nodes

#### Job 
A job is a collection of tasks

You can specify an optional job priority.


#### Application Packages


### Azure Batch service quotas and limits

As with other Azure services, there are limits on certain resources associated with the Batch service.

See details on limits [here](https://docs.microsoft.com/en-us/azure/batch/batch-quota-limit).



### Running Batch jobs with Azure CLI


#### Create Resource group

```bash

az group create \
    --name batchResourceGroup \
    --location norwayeast

``` 



Batch can detect and then retry failed tasks

By default, jobs remain in the active state when all tasks within the job are complete. 


Every request made against the Batch service must be authenticated.