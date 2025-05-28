extra_vars:
  cluster_name: ${{ parameters.cluster_name_custom | lower if parameters.cluster_name == "Cluster(ARO), não encontrado?" else parameters.cluster_name | lower }}
  aro_subscription_id: ${{ parameters.aro_subscription_id_custom | lower if parameters.aro_subscription_id == "SubscriptionID, não encontrado?" else parameters.aro_subscription_id | lower }}
  azure_keyvault_name: ${{ parameters.azure_keyvault_name_custom | lower if parameters.azure_keyvault_name == "Keyvault, não encontrado?" else parameters.azure_keyvault_name | lower }}
  kv_subscription_id: ${{ parameters.kv_subscription_id_custom | lower if parameters.kv_subscription_id == "Keyvault SubscriptionID, não encontrado?" else parameters.kv_subscription_id | lower }}
  rg_aro_cluster: ${{ parameters.rg_aro_cluster_custom | lower if parameters.rg_aro_cluster == "Cluster(ARO) resource group, não encontrado?" else parameters.rg_aro_cluster | lower }}