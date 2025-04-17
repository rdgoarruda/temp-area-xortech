### 🧩 [SubTask] - Apoio na Revisão de Requisitos da Automação – Foco em Secrets e Acesso a Recursos Cloud [CAAS][25R2-OKR1.3]

**Descrição:**  
Subtarefa dedicada à análise e definição dos requisitos relacionados ao uso de Secrets, provisionamento de namespaces e comunicação entre aplicações e recursos da cloud, no contexto da automação de clusters.

---

**Atividades envolvidas:**

- Participação em brainstorming com o time para entendimento da arquitetura atual.
- Contribuição na elaboração de desenhos técnicos (em andamento).
- Reunião com o time de **DS** para alinhamento sobre os requisitos de comunicação e acesso.

---

**Tópicos discutidos:**

- **Políticas de acesso** definidas via **ACM**.
- **Secrets** provenientes do fluxo do **IaC**:
  - Situações em que namespaces foram criados sem a secret necessária, dificultando o deploy.
  - Algumas aplicações já tinham dependência de comunicação com serviços cloud no momento do provisionamento.
- Observação: **nem todas as aplicações precisam de Secret**, mas quando precisam, isso deve estar claro na automação.

---

**Levantamento técnico:**

- Que tipo de informação deve conter a Secret no Kubernetes?
  - `spn`, `id do servicePrincipal` e `senha`
  - Chave para acesso ao **KeyVault**
  - Caso haja armazenamento de **credenciais de banco**, a chave do cofre estará presente na Secret

---

**Links relevantes:**

- Acesso Azure: [safelink](https://statics.teams.cdn.office.net/evergreen-assets/safelinks/1/atp-safelinks.html)
- CloudVRA: https://cloudvra.corp.bradesco.com.br/
- ![Screenshot](anexar-imagem-ilustrativa)

---

**Objetivo:**  
Contribuir para clareza e padronização dos requisitos técnicos relacionados a Secrets e políticas de acesso no fluxo de automação, evitando falhas operacionais e dependências manuais.

**Responsável:**  
*[@seu_nome ou time responsável]*