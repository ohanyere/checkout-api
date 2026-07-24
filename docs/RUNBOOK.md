# Runbook

## Service

- Name: `checkout-api`
- Team: `Platform Engineering`
- Owner: `mooref068@gmail.com`
- Cost center: `platform-engineering`

## First Checks

```bash
kubectl get rollout checkout-api -n checkout-api-dev
kubectl get pods -l app.kubernetes.io/name=checkout-api -n checkout-api-dev
kubectl logs -l app.kubernetes.io/name=checkout-api -n checkout-api-dev
```

## Health

```bash
curl https://checkout-api.dev.platform.ohanyere.internal/healthz
curl https://checkout-api.dev.platform.ohanyere.internal/readyz
curl https://checkout-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo checkout-api -n checkout-api-dev
```

Escalate to `Platform Engineering` through `mooref068@gmail.com` if rollback does not restore service.
