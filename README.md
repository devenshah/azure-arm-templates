# Collection of azure templates

## Prerequisites

### Azure CLI

Execute following command on elevated powershell window  
`Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'`

## Useful links

- [Azure template samples](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell)
- [Azure CLI documentation](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest)

## Steps to deploy azure template using powershell

- Login  
`az login`
- Declare variable  
`$rgName = 'azure-template-rg'`
- Create resource group  
`az group create -l westus -n $rgName`
- Deploy template to the group  
`az group deployment create -g $rgName --template-file azuredeploy.json`
- Clear down  
`az group delete -n $rgName`
