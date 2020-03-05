_https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell_

# Install Azure CLI

`Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'`

# Create Template azuredeploy.json

# Execute command on powershell  
_https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest_
- Login  
`az login`

- Create resource group  
`az group create -l westus -n firsttemplate-rg`

- Deploy template to the group  
`az group deployment create -g firsttemplate-rg --template-file azuredeploy.json`

- Clear down  