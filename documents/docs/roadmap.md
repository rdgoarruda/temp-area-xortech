### Roadmap de Automação do Backstage

## Fase 1: Preparação e Configuração Inicial

   **Entendimento da Ferramenta e Arquitetura**
   - Estudo detalhado sobre a ferramenta Backstage e sua arquitetura.

   **Disponibilização da Infraestrutura**
   - Configuração da infraestrutura necessária para hospedar e rodar o Backstage.

   **Configuração e Testes Iniciais**
   - Instalação e configuração inicial do Backstage e realização de testes.

   **Definições de Padrões Organizacionais**
   - Estabelecimento de padrões organizacionais para nomenclatura, tags e metadados.

   **Elaboração de Modelos de Catálogo**
   - Criação de modelos de catálogo iniciais.

   **Importar Aplicações Iniciais**
   - Importação das primeiras aplicações para o Backstage.

## Fase 2: Automação e Escalabilidade

   **Elaboração de Templates Backstage**
   - Criação de templates utilizando Nunjucks e estudo de padrões.

   **Elaboração de Manifestos Bases**
   - Desenvolvimento de manifestos base para Kubernetes.

   **Infraestrutura do Repositório**
   - Organização da estrutura de repositórios para suportar a automação.

   **Elaboração de Actions para Suporte ao Fluxo de Automação**
   - Desenvolvimento de actions específicas como `acme-update-kustomization.ts` e `acme-bitbucket-commit-and-push.ts`.

   **Customização e Instalação de Plugins**
   - Instalação e customização de plugins como DynamicDataPicker e FormDataBackend.

   **Elaboração de Templates e Scaffolders**
   - Criação de diversos templates e scaffolders para recursos GCP e clusters utilizando Crossplane e Terraform.

   **Estrutura Organizacional do Backstage**
   - Definição da estrutura organizacional no Backstage, incluindo Domínios, Grupos e Usuários.

   **Elaboração de Plugins para Dockerlint e Repoanalyze**
   - Desenvolvimento de plugins personalizados para Dockerlint e Repoanalyze.

   **Criação de Fluxos Automatizados para ArgoCD**
   - Automação da configuração do ArgoCD para o cluster e repositório de manifestos da aplicação através dos templates do Backstage.

   **Templates para Catalogar Aplicações GKE**
    - Desenvolvimento de templates para catalogar aplicações GKE legado e novo padrão.

## Fase 3: Piloto e Expansão 

   **Documentação para Piloto com Squads**
   - Desenvolvimento de documentação para apoiar as squads durante o piloto.

   **Coleta de Informações para Elaboração de Padrões**
   - Coleta de feedback das squads.

   **Consolidar Informações e Melhorias**
   - Análise de feedback e implementação de melhorias.

   **Catalogar Aplicações Existentes de Forma Automática**
   - Automação da catalogação das aplicações existentes.

   **Melhoria Contínua do Catálogo**
   - Ciclo contínuo de melhorias no catálogo.