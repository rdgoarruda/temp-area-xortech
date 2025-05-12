- hosts: localhost
  gather_facts: no
  tasks:

    - name: Set ArgoCD URL and headers
      set_fact:
        argocd_url: https://argocd-server-argo-rollouts.apps.arodvleap02.arocorpp.bradesco.com.br
        api_headers:
          Authorization: "Bearer token"
        argocd_project: namespace-project
        application_name: nstesteasb08

    - name: Wait for application to be Synced and Healthy
      uri:
        url: "{{ argocd_url }}/api/v1/applications/{{ application_name }}-namespace-app"
        method: GET
        headers: "{{ api_headers }}"
        return_content: yes
        validate_certs: no
      register: app_status
      retries: 30
      delay: 10
      until: >
        app_status.json.status.sync.status == "Synced" and
        app_status.json.status.health.status == "Healthy"

    - name: Show final status
      debug:
        msg: "Application is Synced and Healthy: {{ app_status.json.status }}"