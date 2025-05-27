parameters:
  - title: Informações Gerais
    required:
      - nome_namespace
      - usar_cluster_personalizado
      - ambiente
      - domain
      - centro_custo
    properties:
      nome_namespace:
        title: Nome da Namespace
        type: string
        maxLength: 15
        description: Nome único da namespace a ser criada.

      usar_cluster_personalizado:
        title: Deseja informar um nome de cluster personalizado?
        type: boolean
        default: false

      cluster_name:
        title: Nome do Cluster
        type: string
        enum:
          - arodvdagempp111
          - arodvinguap111
          - arodvleap02
          - arodvleap03
          - arodvpdtfnpip111
          - arodvplatfcap111
          - arodvplatfud111
        description: Selecione o cluster ARO onde a namespace será provisionada.

      custom_cluster_name:
        title: Nome do Cluster (customizado)
        type: string
        description: Preencha este campo somente se quiser informar um cluster fora da lista.

    dependencies:
      usar_cluster_personalizado:
        oneOf:
          - properties:
              usar_cluster_personalizado:
                const: false
              cluster_name: {}
          - properties:
              usar_cluster_personalizado:
                const: true
              custom_cluster_name: {}