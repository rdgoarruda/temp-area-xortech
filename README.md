🔧 Namespace não criado: possíveis causas e soluções

Caso o namespace solicitado não seja criado, verifique os seguintes pontos:
	•	Job Template AAP rodou com falhas
▸ Confirme se todas as etapas do Job foram executadas com sucesso.
▸ Verifique se o arquivo values.yaml foi corretamente gerado e commitado no repositório Git.
	•	ArgoCD não sincronizado
▸ Verifique se o values.yaml foi realmente commitado e se a sincronização automática está ativa.
▸ Cheque também se há erros visíveis no painel do ArgoCD.
	•	ApplicationSet não cadastrado
▸ Valide se existe um ApplicationSet responsável pela pasta ou padrão de clusters do namespace solicitado.
	•	Cluster não conectado ao ArgoCD
▸ Certifique-se de que o cluster está registrado e saudável no ArgoCD.
▸ Verifique no menu Clusters se ele aparece como “Connected”.

⸻

🧾 Logs úteis e onde encontrá-los

Abaixo estão os principais locais onde é possível obter logs e diagnósticos úteis para troubleshooting:
	•	Argo CD
▸ Interface Web: verifique o status da Application ou ApplicationSet.
▸ Logs do pod:

Ansible AAP
▸ Interface do Job Template no AAP: verifique as últimas execuções e seus logs detalhados.
	•	Git
▸ Verifique se o values.yaml foi corretamente commitado e está no path esperado.
▸ Valide se não houve erro de sintaxe ou estrutura nos manifests versionados.
	•	Cluster Kubernetes (ARO ou AKS)
▸ Para validação geral do namespace:

