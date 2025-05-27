parameters:
  - title: Informações Gerais
    required:
      - nome_namespace
      - cluster_name
      - ambiente
      - domain
      - centro_custo
    properties:
      nome_namespace:
        title: Nome da Namespace
        type: string
        description: Nome único da namespace a ser criada. Ex.: "centroCusto-sistema ou vila-sistema"
        ui:help: 'Hint: O nome da namespace deve conter no máximo 15 caracteres.'
        ui:autofocus: true
        maxLength: 15

      cluster_name:
        title: Nome do Cluster
        type: string
        description: |
          Nome do cluster ARO onde a namespace será provisionada.

          Para mais detalhes, consulte a documentação oficial em: https://confluence.bradesco.com.br:8443
        enum:
          - arodvdagempp111
          - arodvinguap111
          - arodvleap02
          - arodvleap03
          - arodvpdtfnpip111
          - arodvplatfcap111
          - arodvplatfud111
    ui:options:
      cluster_name:
        allowArbitrary: true