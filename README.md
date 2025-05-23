import streamlit as st
from azure.identity import AzureCliCredential
from azure.mgmt.resource import SubscriptionClient
from azure.mgmt.redhatopenshift import AzureRedHatOpenShiftClient
from azure.mgmt.redhatopenshift.models import OpenShiftCluster

credential = AzureCliCredential()
subscription_client = SubscriptionClient(credential)

st.title("Clusters ARO - Todas as Subscriptions")

data = []

# Iterar sobre todas as subscriptions
for sub in subscription_client.subscriptions.list():
    sub_id = sub.subscription_id
    aro_client = AzureRedHatOpenShiftClient(credential, sub_id)

    try:
        clusters = aro_client.open_shift_clusters.list()
        for cluster in clusters:
            data.append({
                "Subscription": sub.display_name,
                "Cluster Name": cluster.name,
                "Location": cluster.location,
                "Cluster API Server": cluster.apiserver_profile.url if cluster.apiserver_profile else "N/A",
                "Provisioning State": cluster.provisioning_state,
                "Cluster FQDN": cluster.console_profile.url if cluster.console_profile else "N/A"
            })
    except Exception as e:
        st.error(f"Erro ao acessar ARO na subscription {sub.display_name}: {e}")

# Exibir os clusters encontrados
if data:
    st.dataframe(data)
else:
    st.info("Nenhum cluster ARO encontrado.")