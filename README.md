parameters:
  - title: Informações Gerais
    required:
      - nome_namespace
      - ambiente
      - domain
      - centro_custo
      - usar_cluster_personalizado
    properties:
      nome_namespace:
        title: Nome da Namespace
        type: string
        description: Nome único da namespace a ser criada. Ex.: "centroCusto-sistema ou vila-sistema"
        maxLength: 15

      usar_cluster_personalizado:
        title: Deseja informar um nome de cluster personalizado?
        type: boolean
        default: false

      cluster_name:
        title: Nome do Cluster (selecione da lista)
        type: string
        enum:
          - arodvdagempp111
          - arodvinguap111
          - arodvleap02
          - arodvleap03
          - arodvpdtfnpip111
          - arodvplatfcap111
          - arodvplatfud111
        description: Selecione um cluster da lista

      custom_cluster_name:
        title: Nome do Cluster (personalizado)
        type: string
        description: Preencha apenas se estiver usando um nome fora da lista

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