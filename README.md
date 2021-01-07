# AksRBACSample
A sample of how to do Role Based Access Control with Azure Active Directory for Azure Kubernetes Service

The steps are: 
1. Create Server Service Principal (may require special permissions in AAD Tenant)
1. Create Client Service Principal (may require special permissions in AAD Tenant)
1. Create AKS Cluster with RBAC enabled
1. Create AAD Group for administering the cluster in Azure and controlling admin access to the cluster
1. Assign *Azure Kubernetes Service Cluster User Role* to this group
1. Apply rbac role yaml file
    1. This lets admins use *az aks get-credentials --resource-group $AKS_RG --name $AKS_NAME --admin* to get their kubectl credentials
1. Create namespaces for users
1. Set up new AD groups for users
1. Apply namespace roles yaml to create reader and writer roles for the two namespaces
1. Apply the namespace binding yaml to the groups created above
    1. Now users can use *az aks get-credentials --resource-group $AKS_RG --name $AKS_NAME* to get their kubectl credentials

There is further documentation in the *AKS_RBAC_Steps.txt* file