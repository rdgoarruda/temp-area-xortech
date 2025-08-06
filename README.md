apiVersion: argoproj.io/v1alpha1
kind: ApplicationSet
metadata:
  name: acme-infra-digitalcomm-applicationset
  finalizers:
  - resources-finalizer.argocd.argoproj.io
spec:
  generators:
    - git:
        files:
          - path: infra/env/prd-digitalcomm/**/**/acme-infra/1.0.0/**/values.yaml
        repoURL: git@bitbucket.org:acme_ecommerce/br-foundation-infra-global-manifest.git
        revision: HEAD
  goTemplate: true
  goTemplateOptions:
    - missingkey=error
  template:
    metadata:
      name: '{{.path.basename}}-{{index .path.segments 4}}'
    spec:
      destination:
        name: '{{index .path.segments 4}}'
        namespace: '{{.path.basename}}'
      project: '{{index .path.segments 3}}'
      source:
        repoURL: git@bitbucket.org:acme_ecommerce/br-foundation-infra-global-manifest.git
        targetRevision: HEAD
        path: 'helmcharts/charts/infra/acme-infra/{{index .path.segments 6}}'
        helm:
          valueFiles:
            - '$values/{{.path.path}}/values.yaml'
      syncPolicy:
        automated:
          prune: true
          selfHeal: true
        syncOptions:
          - CreateNamespace=true
          - ApplyOutOfSyncOnly=true
          - SkipSchemaValidation=true
        ignoreDifferences:
          - group: apps
            kind: StatefulSet
            jsonPointers:
              - /spec/template/spec/containers/0/resources/requests
              - /spec/template/spec/containers/0/resources/limits