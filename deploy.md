# Intro
- Use this arm template to create a workspace with a vnet and training clusters
- ML workspaces are inteded to be shared. Each user will need to create their own compute instance. We recomend using a Dv3 if you aren't planing to do training locally or a NC6 if you are.

# Instructions
- Generate an [ssh key](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/create-ssh-keys-detailed)
- Click [![Deploy to Azure](https://azurecomcdn.azureedge.net/mediahandler/acomblog/media/Default/blog/deploybutton.png)](https://azuredeploy.net/)
- Upload the ssh key when you are done
## Deploying manually
- If you want to deploy without using this ARM template you will need to follow these [instructions](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-enable-virtual-network#compute-instance)
- Give the compute instances + clusters your compute instances public ssh key and username azureuser

# Details
This template creates the following
- KeyVault
- Storage account
- AppInsight
- Virtual network
- Network security group
- NC6 low pri gpu training cluster
- Dv3 dedicated cpu training cluster

# What does low pri mean?
AML compute offers low-priority compute to reduce the cost of Batch workloads. Low-priority compute make new types of Batch workloads possible by enabling a large amount of compute power to be used for a very low cost.

Low-priority compute take advantage of surplus capacity in Azure.
The tradeoff for using low-priority compute is that that compute may not be available to be allocated or may be preempted at any time, depending on available capacity.
Low-priority compute are offered at a significantly reduced price compared with dedicated compute. For pricing details, see Batch Pricing.



