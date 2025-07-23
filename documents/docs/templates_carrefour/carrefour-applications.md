# Guia do Usuário para Aplicacoes acme

## Introdução
Selecione qual o Flavor da aplicacao que Deseja Criar:

![Template Golang](./images/templates_golang_demo.png)


O template selecionado cria um novo repositório Golang seguindo os padrões acme, incluindo configurações iniciais, estrutura de diretórios e boas práticas recomendadas.

## Preencha as Informações do Componente

**Número da Requisição do Jira**: Insira o número da requisição do Jira. A requisição pode ser solicitada através do portal: [Link para Jira](https://acmebr.atlassian.net/servicedesk/customer/portals).  
  - **Exemplo**: `REQ-12345`  
**Nome do Componente**: Nome único para identificar o componente.  
  - Deve começar pelo nome da squad (middleware, oms, ecomm, mobile, plataforma), seguido pelo nome do componente em letras minúsculas.  
  - **Exemplo**: `middleware-api-example`  
**Descrição do Componente**: Descrição detalhada do propósito do componente.  
**Key do Projeto Bitbucket**: Key do projeto no Bitbucket.  
    - Pode ser consultado através deste [Link](https://engineering-app.cloud.acme.com.br/app/inventory-gcp/bitbucket-6581f4641e52220ca9f7baa0?branch=master) ou diretamente no projeto Bitbucket.  
**Tipo de Componente**: Selecione o tipo de componente.  
**Sistema Associado**: Sistema ao qual o componente está associado.    
**Proprietário do Componente**: Time responsável pelo componente.  
**Torre responsável pelo componente**: Cluster onde será feito o deploy para PRD.  

![Template Golang Form](./images/templates_golang_demo_1.png)

### Revise as Informações

![Template Golang Review](./images/templates_golang_demo_2.png)

## Fluxo Automatizado

O template realiza automaticamente as seguintes ações:

- Obtém o scaffolder da aplicação Golang.
- Cria o repositório no Bitbucket com base nos dados fornecidos.

![Fluxo App](./images/criar_novo_repo.png)

## Imagem do Processo

![Template Golang Run](./images/templates_golang_demo_run.png)

## Links de Saída

- **Repositório**: https://bitbucket.org/acme_ecommerce/${{squad}}-order-writer/src/main/
- **Abrir no Catálogo**: [Link para abrir a aplicação no catálogo do Backstage.](https://backstage.cloud.acme.com.br/catalog?filters%5Bkind%5D=component&filters%5Buser%5D=owned)

![Template Golang Run](./images/templates_golang_demo_repo.png)

---

Este guia cobre os principais passos para utilizar o template "Serviço - Golang acme" no Backstage. Certifique-se de seguir todas as instruções cuidadosamente para garantir que o processo seja executado corretamente.
