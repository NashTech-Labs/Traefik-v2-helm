# DEPLOY TRAEFIK

```bash
helm install -i -f values-internal.yaml traefik-internal --namespace network .

helm install -i -f values-external.yaml traefik-external --namespace network .
```

Two load balancers are created. You can verify them by checking svc
```bash
kubectl get svc -n network
```

## DELETION:
```
helm del traefik-internal -n network

helm del traefik-external -n network
```

## To check for dashboard:
```bash
kubectl get ingressroute -n network
```