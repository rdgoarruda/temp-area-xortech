# INICIO DEPENDENCIES CONDITION

cluster_name: ${{ parameters.cluster_name_custom | lower if parameters.manual_cluster_name == true else parameters.cluster_name | lower }}

aro_subscription_id: ${{ parameters.manual_aro_subscription_id | lower if parameters.manual_aro_subscription_id_custom == true else parameters.aro_subscription_id | lower }}

azure_keyvault_name: ${{ parameters.manual_azure_keyvault_name | lower if parameters.manual_azure_keyvault_name_custom == true else parameters.azure_keyvault_name | lower }}

kv_subscription_id: ${{ parameters.manual_kv_subscription_id | lower if parameters.manual_kv_subscription_id_custom == true else parameters.kv_subscription_id | lower }}

rg_aro_cluster: ${{ parameters.manual_rg_aro_cluster | lower if parameters.manual_rg_aro_cluster_custom == true else parameters.rg_aro_cluster | lower }}

# FIM DEPENDENCIES CONDITION