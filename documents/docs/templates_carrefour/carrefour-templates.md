# O que é um Template no Backstage?

Os Templates de Software do Backstage são uma ferramenta que automatiza e padroniza o processo de criação de componentes de software dentro da plataforma Backstage. Eles permitem que as equipes criem novos microserviços, sites ou outros componentes de software seguindo as melhores práticas da organização desde o início.

- [Solicitar Aplicacoes](./acme-applications.md)
- [Deploy Kubernetes](./acme-deploy-kubernetes.md)
- [Solicitar Recursos GCP](./acme-gcp-resources.md)

![acme Templates](./images/templates.png)

# Principais Funcionalidades:
- **Automação e Padronização**: Os templates simplificam a configuração e o deployment, permitindo que as equipes criem novos projetos com apenas alguns cliques. Isso inclui a configuração automática de repositórios e pipelines de CI/CD, o que ajuda a evitar a complexidade da infraestrutura subjacente e a focar na entrega de valor de negócio.

- **Customização**: Os templates podem ser personalizados para se alinhar aos padrões e ferramentas específicos da organização. Por exemplo, é possível usar diferentes linguagens de programação, sistemas de CI/CD ou provedores de nuvem conforme necessário. Além disso, os templates podem incluir ações customizadas e campos personalizados, permitindo uma flexibilidade significativa na criação de novos componentes.

- **Integração com o Catálogo de Software**:Todos os componentes criados por meio dos templates são automaticamente registrados no catálogo de software do Backstage, facilitando a gestão e a visibilidade dos ativos de software da organização.

- **Suporte a Variáveis e Parâmetros**: Os templates podem solicitar diferentes variáveis de entrada dos usuários, que são então usadas para personalizar os componentes gerados. Essas variáveis podem incluir informações como o nome do repositório, o proprietário e a localização do repositório, entre outras.

- **Ações de Publicação**: Os templates podem definir ações de publicação, como a criação de novos repositórios em plataformas como GitHub ou GitLab, e a submissão de pull requests. Isso é configurado no arquivo app-config.yaml do Backstage.

- **Extensibilidade**: É possível adicionar novos templates ao Backstage, permitindo que as equipes criem e compartilhem templates que atendam às suas necessidades específicas. Os templates são definidos em arquivos YAML e podem incluir uma série de passos que são executados pela infraestrutura de scaffolding do Backstage.