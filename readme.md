# Deploying Windows Containers with Azure Container Instances integrated with Virtual Networks

This repo helps to deploy Windows Containers with Azure Container Instances integrated with Virtual Networks.

## Running this demo

1. Save the Bicep file as main.bicep to your local computer.
2. Deploy the Bicep file using Azure CLI.

### Azure CLI

```shell
az group create --name exampleRG --location eastus
az deployment group create --resource-group exampleRG --template-file main.bicep
```

### Clean up deployment

When no longer needed, use the Azure portal, Azure CLI to delete the container and all of the resources in the resource group.

```shell
az group delete --name exampleRG --yes --no-wait
```

## Important notes

Check the following table to see the maximum number of CPU cores, memory, and storage for each region.

### Windows Server 2016

> 1B and 2B hosts have been deprecated for Windows Server 2016. See [Host and container version compatibility](/virtualization/windowscontainers/deploy-containers/update-containers#host-and-container-version-compatibility) for more information on 1B, 2B, and 3B hosts.

| Region |3B Max CPU | 3B Max Memory (GB) | Storage (GB) |
| -------- | :----: | :-----: | :-------: |
| Australia East | 2 | 8 | 20 |
| Brazil South | 4 | 16 | 20 |
| Canada Central  | 2 | 3.5 | 20 |
| Central India | 2 | 3.5 | 20 |
| Central US | 2 | 3.5 | 20 |
| East Asia | 2 | 3.5 | 20 |
| East US | 2 | 8 | 20 |
| East US 2 | 4 | 16 | 20 |
| Japan East | 4 | 16 | 20 |
| Korea Central | 4 | 16 | 20 |
| North Central US | 4 | 16 | 20 |
| North Europe | 2 | 8 | 20 |
| South Central US | 2 | 8 | 20 |
| Southeast Asia | 2 | 3.5 | 20 |
| South India | 2 | 3.5 | 20 |
| UK South | 2 | 3.5 | 20 |
| West Central US | 2 | 8 | 20 |
| West Europe | 4 | 16 | 20 |
| West US | 2 | 8 | 20 |
| West US 2 | 2 | 3.5 | 20 |

### Windows Server 2019 LTSC

> 1B and 2B hosts have been deprecated for Windows Server 2019 LTSC. See [Host and container version compatibility](/virtualization/windowscontainers/deploy-containers/update-containers#host-and-container-version-compatibility) for more information on 1B, 2B, and 3B hosts.

| Region | 3B Max CPU | 3B Max Memory (GB) | Storage (GB) | Availability Zone support |
| -------- | :----: | :-----: | :-------: | :-------: |
| Australia East | 4 | 16 | 20 | Y |
| Brazil South | 4 | 16 | 20 | Y |
| Canada Central | 4 | 16 | 20 | N |
| Central India | 4 | 16 | 20 | N |
| Central US | 4 | 16 | 20 | Y |
| East Asia | 4 | 16 | 20 | N |
| East US | 4 | 16 | 20 | Y |
| East US 2 | 4 | 16 | 20 | Y |
| France Central | 4 | 16 | 20 | Y |
| Japan East | 4 | 16 | 20 | Y |
| Korea Central | 4 | 16 | 20 | N |
| North Central US | 4 | 16 | 20 | N |
| North Europe | 4 | 16 | 20 | Y |
| South Central US | 4 | 16 | 20 | Y |
| Southeast Asia | 4 | 16 | 20 | Y |
| South India | 4 | 16 | 20 | N |
| UK South | 4 | 16 | 20 | Y |
| West Central US | 4 | 16 | 20 | N |
| West Europe | 4 | 16 | 20 | Y |
| West US | 4 | 16 | 20 | N |
| West US 2 | 4 | 16 | 20 | Y |
| West US 3| 4 | 16 | 20 | Y |

More information at [https://learn.microsoft.com/en-us/azure/container-instances/container-instances-region-availability](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-region-availability)

