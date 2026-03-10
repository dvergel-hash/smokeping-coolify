
# SmokePing + smokeping_prober + Prometheus para Coolify

## Estructura
- `docker-compose.yml`
- `smokeping/` → montado en `/config` del contenedor SmokePing
- `prober/targets.yaml` → montado en `/config/targets.yaml` del prober
- `prometheus/prometheus.yml` → montado en `/etc/prometheus/prometheus.yml`

## Notas
- Algunos destinos pueden bloquear ICMP. Si ves 100% de pérdida, probá cambiar el host por un dominio `status.*` o un DNS anycast.
- Publicá `smokeping` y/o `prometheus` desde Coolify → Domains.
- Para Grafana, agregá como datasource el Prometheus y usá queries con las métricas `smokeping_*`.
