## Install and setup terraform: 
[Install Terraform CLI for VS code](https://learn.hashicorp.com/tutorials/terraform/install-cli)  
[Install Terraform on local box](https://chocolatey.org/packages/terraform#versionhistory)  
[Sign into your Azure Account](https://docs.microsoft.com/en-us/cli/azure/authenticate-azure-cli?view=azure-cli-latest)  
[Install Azure CLI](https://aka.ms/installazurecliwindows)

## see what account is currently on:

`az account show --output jsonc`

## Confirm you are running required/pinned version of terraform

`terraform version`

## Login to Azure with:

`az login`

## If you have multiple Azure subscriptions, select the one you wish to work with:

`az account set --subscription [my-azure-subscription-guid]`

## Check your default subscription with:

`az account show --output jsonc`
