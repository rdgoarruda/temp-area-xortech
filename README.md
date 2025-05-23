import streamlit as st
import pandas as pd
from azure.identity import AzureCliCredential
from azure.mgmt.resource import SubscriptionClient
from azure.mgmt.redhatopenshift import AzureRedHatOpenShiftClient

credential = AzureCliCredential()
subscription_client = SubscriptionClient(credential)

st.title("Clusters ARO por Tenant")

placeholder = st.empty()  # Espaço reservado para a tabela
data = []

# Lista subscriptions do tenant
subscriptions = list(subscription_client.subscriptions.list())

progress = st.progress(0)
total = len(subscriptions)

for idx, sub in enumerate(subscriptions):
    sub_id = sub.subscription_id
    sub_name = sub.display_name
    tenant_id = sub.tenant_id

    aro_client = AzureRedHatOpenShiftClient(credential, sub_id)

    try:
        clusters = aro_client.open_shift_clusters.list()
        for cluster in clusters:
            data.append({
                "Tenant ID": tenant_id,
                "Subscription Name": sub_name,
                "Subscription ID": sub_id,
                "Cluster Name": cluster.name,
                "Resource Group": cluster.id.split("/")[4],
                "Location": cluster.location,
                "Console URL": cluster.console_profile.url if cluster.console_profile else "N/A"
            })
            # Atualiza a tabela na tela dinamicamente
            df = pd.DataFrame(data)
            placeholder.dataframe(df)
    except Exception as e:
        st.warning(f"[{sub_name}] erro ao buscar clusters: {e}")

    progress.progress((idx + 1) / total)

st.success("Consulta finalizada.")