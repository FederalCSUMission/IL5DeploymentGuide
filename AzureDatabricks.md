## Azure Databricks Deployment Guide
#### This guide was put together with the intent of assisting with Azure Databricks deployments up to IL5 compliancy. 

# Pre-requsites
https://learn.microsoft.com/en-us/azure/azure-government/documentation-government-impact-level-5

### Creating an Azure Databricks workspace
1. In the Azure portal, select *Create a resource*->*Analytics*->*Azure Databricks*.
2. Under **Azure Databricks Service**, provide the values to create a Databricks workspace.
      - Workspace Name - Provide a name for your Databricks workspace
      - Subscription - From the drop-down, select your Azure subscription.
      - Resource Group - Specify whether you want to create a new resource group or use an existing one. A resource group is a container that holds related resources for an Azure solution.
      - Location - Select the location\region closest to your location.
      - Pricing Tier - Select the pricing tier that makes sense for the workload being deployed.
3. Once the following information has been inputted, click *Next* at the bottom of the page to be directed into the networking portion of the Azure Databricks workspace. 
**Please take note that a virtual network is created and managed by default when configuring an Azure Databricks workspace, however a seperate VNet can be created and assigned after the fact if needed.**
      - Deploy Azure Databricks workspace in your own Virtual Network (VNet): Select Yes or No
      - Virtual Network: Select the virtual network the Azure Databricks workspace should be connected to.
**Two subnets will be created in your Virtual Network. Implicit delegation of both subnets will be done to Azure Databricks on your behalf. This means that Azure Databricks will assign and create two separate subnets. One for the public space, one for the private space.**
      - Public Subnet Name: Name of the Public subnet being created.
      - Public Subnet CIDR range: Select any CIDR range allocated for this.
      - Private Subnet Name: Name of the Private subnet being created.
      - Private Subnet CIDR Range: Select any CIDR range allocated for this.
4. Once the deployment has been completed, navigate to the Azure Databricks resource within the Azure portal. 

3. Select **Review + Create**, and then Create. 

## Assigning a Virtual Network to Azure Databricks workspace. 
#### This is needed to support IL5 compliance with network isolation requirements.

1. If a virtual network has not already been created, please follow the steps below to create one. Please take note that a virtual network is created and managed by default when configuring an Azure Databricks workspace. If a new VNet is required, these steps outline creating your own separate virtual network separate from the installation for management purposes.
2. 

### Creating a Spark cluster in Databricks
#### This is needed for standard operations within Azure Databricks and will be important as certain security protocols will need to be deployed against a cluster to meet IL5 compliancy.

1. In the Azure portal, go to the Databricks workspace that was created. and click **Launch Workspace**.
2. This will redirect to the Azure Databricks portal. From the portal, click **New Cluster**. 
3. In the **New Cluster** page, provide the values to create a cluster.
      - Cluster Name - Name of the cluster
      - Cluster Mode - Type of cluster
      - Pool
      - Databricks runtime version -
      - Autopilot Options
          - Enable Autoscaling
          - Terminate after ** minutes of inactivity
      - Worker Type: Selection of worker nodes with type of nodes needed to support the workload.
      - Driver Type: Same as worker nodes.


