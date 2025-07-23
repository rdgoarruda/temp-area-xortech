# Tags

As Tags podem ser usadas para agrupar componentes por tecnologia, equipe, domínio, ambiente, ou qualquer outro critério relevante.  

![acme Catalog](../images/tags.png)

Exemplo de tags para Component::

```
apiVersion: backstage.io/v1alpha1
kind: Component
metadata:
  name: ...
  description: |
    ...
  links:
    - ...
  tags:
    - coretax-admin
    - backend
    - api
    - java
    - br-apps-fiscal-coretax
    - br-apps-fiscal-coretax-be
  annotations:
    ...
spec:
  type: ...
  lifecycle: ...
  owner: ...
  system: ...
  providesApis:
    - ...
  dependsOn: 
    - ...
```

<img align="right" width="150" height="150" src="https://backstage.cloud.acme.com.br/static/acme_branco.895b1e3e..png">