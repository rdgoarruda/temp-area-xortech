01. [Arquitetura] - Argo CD Automações CaaS
Objetivo
Este documento apresenta a arquitetura proposta para as automações de GitOps com Argo CD no contexto da plataforma CaaS (Container as a Service). O foco está na separação de responsabilidades entre times, controle de ambientes e escalabilidade da solução.

Visão Geral da Arquitetura
A arquitetura é dividida em dois domínios principais:

1. Produtos
Responsável por aplicações desenvolvidas pelos times de produto. Possui instâncias ArgoCD distintas para:

Desenvolvimento / Homologação (DV/HO): argocd-dv e argocd-ho

Produção (PRD): argocd-prd

Cada instância gerencia múltiplos AppSets por produto:

Copy
Edit
{caas-produto1}, {caas-produto2}, ..., {caas-produtoN}
2. Tools
Responsável por ferramentas e componentes compartilhados, como observabilidade, segurança e finops. Também possui instâncias ArgoCD separadas por ambiente:

argocd-dv, argocd-ho, argocd-prd

Cada AppSet gerencia ferramentas por tipo:

pgsql
Copy
Edit
{caas-tools}, {security-tools}, {observability-tools}, {finops-tools}, etc.
Organização dos Repositórios Git
A estrutura do repositório Git foi desenhada para suportar múltiplos ambientes e domínios de forma escalável e modular.

bash
Copy
Edit
providers/
└── azure/                           # Provedor (Azure, AWS, etc.)
    ├── _overlays/                  # Aplicações raiz do ArgoCD por ambiente
    │   ├── argocd-apps-of-apps-dv.yaml
    │   ├── argocd-apps-of-apps-ho.yaml
    │   ├── argocd-apps-of-apps-pr.yaml
    │   ├── dv/kustomization.yaml
    │   ├── ho/kustomization.yaml
    │   └── pr/kustomization.yaml
    └── adqemp/                     # Domínio/BU
        └── clusters/               # Agrupamento por tipo de recurso
            ├── dv/
            │   └── arodvademppii/
            │       ├── .gitkeep
            │       ├── teste-namespace/
            │       │   └── values.yaml
            │       ├── kustomization.yaml
            │       └── namespace-appset-arodvademppii.yaml
            ├── ho/
            │   └── arohoademppii/
            │       └── ...
            └── pr/
                └── aroprdademppii/
                    └── ...
Convenções:
Clusters organizados por ambiente (dv, ho, pr)

Cada cluster possui seu próprio AppSet

Padrão de nomenclatura facilita automações e leitura humana

Benefícios da Arquitetura Proposta
Segregação clara de ambientes e responsabilidades

Escalabilidade horizontal com novos AppSets

Governança centralizada via GitOps

Padronização entre produtos e ferramentas

Separação entre times de produto e time de plataforma (Tools)
