# O que é Catálogo no Backstage?

O Catálogo do Backstage é uma ferramenta centralizada que organiza todos os componentes de software da nossa organizacao – como serviços, apis, recursos, documentações e squads – em um único local acessível. 

Imagine-o como uma biblioteca digital onde cada livro é um recurso diferente que a sua organização cria e mantém. 

Assim como uma biblioteca organiza os livros por seções, o catálogo do Backstage organiza os recursos de software de forma que todos possam encontrá-los e entendê-los facilmente.

![acme Catalog](../kinds/images/catalog.png)

---

## Para que Serve?

Num nível organizacional, o catálogo serve a vários propósitos importantes:

- **Visibilidade**: Fornece uma visão clara de todos os recursos de software disponíveis dentro da empresa, quem os mantém, e como eles se encaixam no ecossistema maior. Isso ajuda a evitar duplicações de esforço e facilita a descoberta de ferramentas ou serviços que podem ser reutilizados em diferentes projetos.

- **Padronização**: Ajuda a implementar padrões através da organização ao fornecer modelos e práticas recomendadas para o desenvolvimento e a manutenção de software. Isso garante que todos estejam alinhados e contribuam para a coesão e eficiência operacional.

- **Autosserviço**: Empodera as equipes a publicar e atualizar suas próprias informações no catálogo, promovendo a autonomia e a responsabilidade. Isso reduz gargalos operacionais e incentiva a atualização constante e a precisão das informações.

- **Colaboração**: Facilita a colaboração entre equipes ao tornar transparente quem está trabalhando em quê. Isso permite que as equipes se conectem mais facilmente para colaborar ou compartilhar conhecimentos.

---

## Como Funciona?

O catálogo é alimentado por metadados – informações sobre os recursos de software que ajudam a definir o que eles são, como são usados, e quem é responsável por eles. Esses metadados são geralmente armazenados em arquivos YAML junto com o código fonte do recurso, permitindo que sejam facilmente atualizados pelos desenvolvedores.

Quando um novo recurso é adicionado ao catálogo, ele passa por um processo de ingestão que lê esses metadados e os apresenta de forma legível no Backstage. A partir daí, qualquer pessoa na organização pode buscar e explorar os recursos disponíveis, entender suas funcionalidades e saber como acessá-los ou contribuir para eles.

## Entidades Backstage

 No Backstage, diversos tipos de entidades podem ser catalogados para oferecer uma visão clara e organizada do ecossistema de desenvolvimento de software.  

- [Componentes](../kinds/components.md)
- [Apis](../kinds/apis.md)
- [Resources](../kinds/resources.md)

<img align="right" width="150" height="150" src="https://backstage.cloud.acme.com.br/static/acme_branco.895b1e3e..png">