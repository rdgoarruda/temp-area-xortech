- name: 01. Obter kubeconfig do cluster AKS via Azure CLI
  ansible.builtin.shell: >
    az aks get-credentials
    --resource-group {{ aks_resource_group }}
    --name {{ cluster_name }}
    --file /tmp/aks-{{ cluster_name }}.kubeconfig
    --overwrite-existing
  register: aks_kubeconfig_result
  changed_when: "'Merged' in aks_kubeconfig_result.stdout"

- name: 02. Listar namespaces para validar o kubeconfig
  ansible.builtin.shell: >
    kubectl get namespaces
    -o jsonpath='{.items[*].metadata.name}'
  environment:
    KUBECONFIG: /tmp/aks-{{ cluster_name }}.kubeconfig
  register: aks_namespaces
  changed_when: false
  failed_when: aks_namespaces.rc != 0

- name: 03. Exibir namespaces encontrados
  ansible.builtin.debug:
    var: aks_namespaces.stdout_lines