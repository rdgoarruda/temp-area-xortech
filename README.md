- name: Listar todos os Key Vaults na subscription
  azure.azcollection.azure_rm_keyvault_info:
    client_id: "{{ lookup('ansible.builtin.env', 'az_clt_id') }}"
    secret: "{{ lookup('ansible.builtin.env', 'az_clt_secret') }}"
    tenant: "{{ lookup('ansible.builtin.env', 'az_tnt') }}"
    subscription_id: "{{ kv_subscription_id }}"
  register: all_vaults
  when: consulta_keyvault | bool

- name: DEBUG: all_vaults
  debug:
    var: all_vaults
  when: consulta_keyvault | bool

- name: Extrair resource_group do Key Vault informado
  ansible.builtin.set_fact:
    azure_keyvault_rg: >-
      {{ all_vaults.key_vaults
          | selectattr('name', 'equalto', azure_keyvault_name)
          | map(attribute='resource_group')
          | first }}
  when: consulta_keyvault | bool

- name: Verificar se o Key Vault existe
  fail:
    msg: "O Key Vault '{{ azure_keyvault_name }}' não foi encontrado na subscription '{{ kv_subscription_id }}'."
  when: consulta_keyvault | bool and (azure_keyvault_rg is not defined or azure_keyvault_rg == "")  # valida se não encontrou

- name: Obter informações do Key Vault na Azure
  azure.azcollection.azure_rm_keyvault_info:
    client_id: "{{ lookup('ansible.builtin.env', 'az_clt_id') }}"
    secret: "{{ lookup('ansible.builtin.env', 'az_clt_secret') }}"
    tenant: "{{ lookup('ansible.builtin.env', 'az_tnt') }}"
    subscription_id: "{{ kv_subscription_id }}"
    resource_group: "{{ azure_keyvault_rg }}"
    name: "{{ azure_keyvault_name }}"
  register: kv_info
  when: consulta_keyvault | bool

- name: DEBUG: kv_info
  debug:
    var: kv_info
  when: consulta_keyvault | bool


- name: Extrair resource_group do Key Vault
  ansible.builtin.set_fact:
    azure_keyvault_rg: >-
      {{ all_vaults.keyvaults
          | selectattr('name', 'equalto', azure_keyvault_name)
          | map(attribute='resource_group')
          | first }}
  when: consulta_keyvault | bool



