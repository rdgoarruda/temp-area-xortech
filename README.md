- hosts: localhost
  gather_facts: no
  tasks:

    - name: Set ArgoCD URL and headers
      set_fact:
        argocd_url: https://argocd-server-argo-rollouts.apps.arodvleap02.arocorpp.bradesco.com.br
        api_headers:
          Authorization: "Bearer token"
        application_name: nstesteasb08

    - name: Wait until the Application is created
      uri:
        url: "{{ argocd_url }}/api/v1/applications/{{ application_name }}-namespace-app"
        method: GET
        headers: "{{ api_headers }}"
        return_content: yes
        status_code: 200
        validate_certs: no
      register: app_response
      retries: 30
      delay: 5
      until: app_response.status == 200

    - name: Wait until Application is Synced and Healthy
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
        (app_status.json.status is defined) and
        (app_status.json.status.sync.status == "Synced") and
        (app_status.json.status.health.status == "Healthy")

    - name: Show final status
      debug:
        msg: "Application is Synced and Healthy: {{ app_status.json.status }}"