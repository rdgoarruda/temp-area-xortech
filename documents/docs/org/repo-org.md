# Estrutura de Diretório Organizacional

A seguir, apresentamos uma introdução à estrutura de diretório proposta para a organização br-apps-backstage-organization, projetada para facilitar a navegação, a descoberta e a manutenção dos componentes do Backstage.

```
acme
├── acme-domains.yaml
├── acme-gcpprojects.yaml
├── acme-groups.yaml
├── acme-resources.yaml
├── acme-systems.yaml
├── clusters
│   ├── br-app-scango-prod-priv-002.yaml
│   ├── br-app-scango-qa-priv-001.yaml
│   ├── ...
├── documents
│   ├── acme-doc.yaml
│   ├── docs
│   └── mkdocs.yml
├── domains
│   ├── ecommerce-domain.yaml
│   └── lojas-domain.yaml
├── groups
│   ├── acme-corp.yaml
│   ├── devops.yaml
│   ├── ...
│   └── towers
│       ├── acmao.yaml
│       ├── acme.yaml
│       └── digicomm.yaml
├── org.yaml
├── projects
│   ├── br-apps-scango-prd.yaml
│   ├── br-apps-scango-qa.yaml
│   ├── ...
├── systems
│   ├── base-system.yaml
│   ├── br-app-scango.yaml
│   ├── ...
└── users
    └── users.yaml
```

# Descrição dos Diretórios

**documents:** Contém esta documentação.

**domains:** Agrupa as definições YAML para diferentes domínios de negócios dentro da organização, como Digital, Finance, Marketing, Plataforma e Tax. Esses arquivos YAML facilitam a categorização e organização dos serviços e componentes do Backstage.

**squads:** Contém arquivos YAML para diferentes equipes ou "squads" dentro da organização, descrevendo os serviços ou componentes pelos quais cada equipe é responsável.

**systems:** Contém arquivos YAML que definem os diferentes sistemas dentro da organização. Esses arquivos facilitam a gestão e organização dos sistemas que integram os diversos componentes e serviços do Backstage.

**templates:** Armazena os templates do Backstage usados para criar novos serviços, componentes, websites, e outros objetos no Backstage. O subdiretório backstage é reservado para templates específicos do Backstage.



<img align="right" width="150" height="150" src="https://backstage.cloud.acme.com.br/static/acme_branco.895b1e3e..png">