- name: DEBUG: ID do Key Vault encontrado
  debug:
    msg: >-
      {{
        all_vaults.keyvaults
        | selectattr('name', 'equalto', azure_keyvault_name)
        | map(attribute='id')
        | list
        | first
      }}
  when: consulta_keyvault | bool

- name: Extrair resource_group do Key Vault a partir do ID
  ansible.builtin.set_fact:
    azure_keyvault_rg: >-
      {{
        (
          all_vaults.keyvaults
          | selectattr('name', 'equalto', azure_keyvault_name)
          | map(attribute='id')
          | list
          | first
          | default('')
          | regex_findall('/resourceGroups/([^/]+)')
          | first
          | default('')
        )
      }}
  register: azure_keyvault_rg_task
  when: consulta_keyvault | bool