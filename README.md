steps:
  - id: fetch-base
    name: Fetch Base
    if: >-
      ${{ [
        'email1@acme.com.br',
        'email2@acme.com.br',
        'email3@acme.com.br',
        'email4@acme.com.br',
        'email5@acme.com.br',
        'email6@acme.com.br',
        'email7@acme.com.br',
        'email8@acme.com.br',
        'email9@acme.com.br',
        'email10@acme.com.br',
        'email11@acme.com.br',
        'email12@acme.com.br',
        'email13@acme.com.br',
        'email14@acme.com.br',
        'email15@acme.com.br',
        'email16@acme.com.br',
        'email17@acme.com.br',
        'email18@acme.com.br',
        'email19@acme.com.br',
        'email20@acme.com.br'
      ].includes(context.user?.profile?.email)
      ||
      [
        'email21@acme.com.br',
        'email22@acme.com.br',
        'email23@acme.com.br',
        'email24@acme.com.br',
        'email25@acme.com.br',
        'email26@acme.com.br',
        'email27@acme.com.br',
        'email28@acme.com.br',
        'email29@acme.com.br',
        'email30@acme.com.br',
        'email31@acme.com.br',
        'email32@acme.com.br',
        'email33@acme.com.br',
        'email34@acme.com.br',
        'email35@acme.com.br',
        'email36@acme.com.br',
        'email37@acme.com.br',
        'email38@acme.com.br',
        'email39@acme.com.br',
        'email40@acme.com.br'
      ].includes(context.user?.profile?.email) }}
    action: fetch:template
    input:
      url: ./base

---

parameters:
  - title: Informações do projeto
    required:
      - name
    properties:
      name:
        type: string
        description: Nome do projeto

steps:
  - id: fetch-base
    name: Fetch Base
    if: >-
      ${{ [
        'email1@acme.com.br',
        'email2@acme.com.br',
        'email3@acme.com.br'
      ].includes(context.user?.profile?.email) }}
    action: fetch:template
    input:
      url: ./base
