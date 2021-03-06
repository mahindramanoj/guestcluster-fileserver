# guestcluster-fileserver
This repo contains the linked arm template to deploy resources in Azure to setup a guest cluster file server. It also has the powershell module that does the post-configuration to create the cluster file server in Azure using powershell interactively.

# Prerequisites
1. An Azure subscription
2. A resource group with a virtual network already deployed that has enough Ips available for use.
3. A storage account with a container that has all the files that are available under artifacts folder in this repo.
4. User deploying this template need to be a contributor scroped either at subscription or resource-group that will be used.
5. A DC should already be deployed and the Ip should be added to Vnet custom dns for the cluster nodes to be able to join to the vm. If thinking to use on-prem DC, a vpn or express-route connectivity is needed with its IP as the custom DNS server of the vnet.
6. If the subnet has an NSG associated that blocks outbound internet connectivity, open outbound connectiivty azure storage.

# Note
Update customScript.ps1 that is availabe in artifacts folder with the storage account that has both the azcopy.exe file and AzureStorageSpacesDirectClusterShare powershell module. Ensure to update the fileUri value with the desired storage account in vmdeploy.json file. 
