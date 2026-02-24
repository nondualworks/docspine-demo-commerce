# Deploy Checkout API

Step-by-step guide for deploying the Checkout API to production.

## Prerequisites

- Access to the `checkout` namespace in Kubernetes
- `kubectl` configured for the target cluster
- Valid AWS credentials for ECR image pull

## Steps

1. Merge your PR to `main`
2. CI pipeline builds and pushes the container image to ECR
3. ArgoCD detects the new image tag and initiates sync
4. Verify the deployment: `kubectl get pods -n checkout`
5. Run smoke tests: `just test-smoke`

## Rollback

If the deployment fails health checks, ArgoCD will automatically rollback to the previous version within 5 minutes.
