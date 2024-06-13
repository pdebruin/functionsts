# functionsts

## 1 HTTP
This sample shows an Azure Function in TypeScript with an http trigger.

### Build and run locally
```
func init --typescript
func new --name HttpExample --template "HTTP trigger" --authlevel "anonymous"
npm start
```

### Deploy to Azure
```
region=northeurope
resourcegroup=functionsts1
storageaccount=functionsts1sa
nodeversion=20
functionapp=functionsts1fa
az group create --name $resourcegroup --location $region
az storage account create --name $storageaccount --location $region --resource-group $resourcegroup 
az functionapp create --resource-group $resourcegroup --consumption-plan-location westeurope --runtime node --runtime-version $nodeversion --functions-version 4 --name $functionapp --os-type linux --storage-account $storageaccount
func azure functionapp publish $functionapp
```

[Source](https://learn.microsoft.com/azure/azure-functions/create-first-function-cli-typescript)

[Home](../README.md)