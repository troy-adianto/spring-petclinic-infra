TODO:
1. Use External Registry (Done)
2. Trim Commit ID (Done)
3. Scan ACN (Done)
4. Promote to UAT pipeline
    - trigger
5. Promote to Prod pipeline
    - trigger
6. add secret to webhook
7. sealed secret
8. use helm/developer hub to generate?
9. use resolver?


DEPLOYMENT STEPS
- create namespace
   - quarkus-hello-ci
   - quarkus-hello-dev
   - quarkus-hello-uat
   - quarkus-hello-prod
- Install Openshift Pipeline Operator
- Install Advance Cluster Security Operator
- Create robot account to registry (eg. quay.io)
- configure ACS 
    - Create token
    - Configure registry integration
    - disable enforcement on fixable at least important policy
- Create Secrets
    - Github Secret
    - Quay Registry Secret
    - ACS secret (add port to acs endpoint)
    - Webhook secret (optional)
- Provide pipeline sa privilege to
    - Internal/external registry (update service account pull secret)
    - destination pipeline privileges
- Create the following resources
    - pvc.yaml
    - tasks/task.yaml
    - build-and-deploy-dev.yaml
    - promote-to-prod.yaml
    - promote-to-uat.yaml
    - trigger/*.yaml
    - role-binding.yaml
- configure github webhook