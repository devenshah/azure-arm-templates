# Collection of azure templates

## Prerequisites

- Azure CLI  
Execute following command on elevated powershell window  
`Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'`
- Powershell  

## Useful links

- [Azure template samples](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell)
- [Azure CLI documentation](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest)

## Steps to deploy azure template using powershell

- Login  
`az login` or `az login --use-device-code`
- Declare variable  
`$rgName = 'azure-template-rg'`  
`$rgLocation = 'eastus'`
- Create resource group  
`az group create -l $rgLocation -n $rgName`
- Validate template before deployment  
`az group deployment validate -g $rgName --template-file azuredeploy.json --parameters location=$rgLocation`
- Deploy template to the group  
  - add following to see logs, the logs are also available on the portal
    `-- debug`
`az group deployment create -g $rgName --template-file azuredeploy.json`
  - add following for parameters  
    `--parameters location=$rgLocation`
- Clear down  
`az group delete -n $rgName`
