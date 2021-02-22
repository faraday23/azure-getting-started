## Create new resource group:
`az group create -l eastus -n myaksrg`


## Create vnet:
```
az network vnet create --resource-group 491-b8c1e496-deploying-and-accessing-an-applicatio --name MyVnet --address-prefix 10.0.0.0/16 --subnet-name default --subnet-prefix 10.0.0.0/24
```


## Get subnet resource ID:
```
az network vnet subnet list --resource-group 491-b8c1e496-deploying-and-accessing-an-applicatio --vnet-name myVnet --query "[0].id" --output tsv
```

## Create AKS cluster with Azure CNI:
```
az aks create \
  --resource-group 491-b8c1e496-deploying-and-accessing-an-applicatio \
  --name azurecniCluster \
  --network-plugin azure \
  --vnet-subnet-id "/subscriptions/4cedc5dd-e3ad-468d-bf66-32e31bdb9148/resourceGroups/491-b8c1e496-deploying-and-accessing-an-applicatio/providers/Microsoft.Network/virtualNetworks/MyVnet/subnets/default" \
  --docker-bridge-address 172.17.0.1/16 \
  --dns-service-ip 10.0.8.10 \
  --service-cidr 10.0.8.0/21 \
  --generate-ssh-keys \
  --service-principal "20b16c1d-9c6b-4400-9cf1-f5c67f2621f7" \
  --client-secret "_0fl65Okt1WrY.6-oiiRU.MQRJ.lD1u43O"
  ```
