## Azure Key Vault Deployment Guide

### This aspect is crucial to securing data services and having them adhere to any DoD impact level compliancy. The instructions below discusses how to deploy the service, however throughout the guide, we will be providing steps on how to implement Azure Key Vault against our respective services.

### Creating an Azure Key Vault

1. From the Azure Portal menu, select --> Create a Resource.
2. Within the Search box, enter Key Vault.
3. From the results list, choose Key Vault.
4. Within the Key Vault section, choose Create. This will redirect to a new screen where details for the Key Vault will need to be provided. 
  - Name: A unique name is required.
  - Subscription: Subscription where the resource will be deployed into.
  - Within Resource Group, select existing RG or "Create New" if needed.
  - Location: Select a location where this resource will be deployed into.
  - Other options can be left to default.
5. Once this information has been provided, select **Create**.

**Please capture the Vault Name and Vault URI as those pieces of information will be leveraged when securing secrets throughout other data services**.
