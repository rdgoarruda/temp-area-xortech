- name: Listar todos os Key Vaults na subscription
  azure.azcollection.azure_rm_resource_info:
    client_id: "{{ lookup('ansible.builtin.env', 'az_clt_id') }}"
    secret: "{{ lookup('ansible.builtin.env', 'az_clt_secret') }}"
    tenant: "{{ lookup('ansible.builtin.env', 'az_tnt') }}"
    subscription_id: "{{ kv_subscription_id }}"
    api_profile: "latest"
    provider: "Microsoft.KeyVault"
    resource_type: "vaults"
  register: all_vaults
  when: consulta_keyvault | bool