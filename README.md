from azure.identity import AzureCliCredential
from azure.mgmt.resource import SubscriptionClient
from azure.mgmt.redhatopenshift import AzureRedHatOpenShiftClient
import pandas as pd

# Autenticação via Azure CLI
credential = AzureCliCredential()
subscription_client = SubscriptionClient(credential)

# Lista consolidada
clusters_info = []

# Itera sobre todas as subscriptions
for sub in subscription_client.subscriptions.list():
    sub_id = sub.subscription_id
    aro_client = AzureRedHatOpenShiftClient(credential, sub_id)

    try:
        clusters = aro_client.open_shift_clusters.list()
        for cluster in clusters:
            clusters_info.append({
                "Nome": cluster.name,
                "Tipo": "Cluster do Red Hat OpenShift no Azure",
                "Grupo de Recursos": cluster.id.split("/")[4],  # Extrai do ID
                "Localização": cluster.location
            })
    except Exception as e:
        print(f"Erro na subscription {sub.display_name}: {e}")

# Exibe como tabela
df = pd.DataFrame(clusters_info)
print(df)

# (Opcional) Salvar CSV igual ao portal
df.to_csv("clusters_aro.csv", index=False)