_https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell_

# Install Azure CLI

`Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'`

# Create Template azuredeploy.json

# Execute command on powershell  
_https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest_
- Login (in browser)  
`az login`
- Declare variable  
`$rgName = 'azure-template-rg'`
- Create resource group  
`az group create -l westus -n $rgName`
- Deploy template to the group  
`az group deployment create -g $rgName --template-file azuredeploy.json`
- Clear down  
`az group delete -n $rgName