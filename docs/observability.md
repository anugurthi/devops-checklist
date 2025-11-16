# Observability (MLT Stack) Checklist

## Metrics (Prometheus + Grafana)
- HA Prometheus; service discovery; recording rules; long-term storage (Thanos/Cortex)
- RED & USE metrics; Golden Signals; business KPIs
- Exporters: node, blackbox, db, cloud provider
- Grafana dashboards as code; environment variable templating

## Logging (Loki / ELK)
- Structured JSON logs; correlation IDs; centralized aggregation
- ELK: ILM, Kibana visualization, retention tiers
- Loki: Promtail agents, efficient labeling, object storage backend
- Cloud-native logging integration (CloudWatch, etc.)

## Tracing (OpenTelemetry + Jaeger/Tempo)
- SDK integrated & auto-instrumentation; custom spans; sampling strategy
- Resource attributes (service.name, environment)
- Jaeger or Tempo backend; retention configured

## Unified Platform
- Grafana stack integration (Prometheus + Loki + Tempo + Agent)
- Jump links between metrics/logs/traces via trace IDs

## Alerting & SLOs
- Symptom-based alerts; multi-burn-rate SLO alerts
- Alertmanager HA; routing, inhibition, silences
- Error budget dashboards & depletion alerts

## Incident Response
- On-call rotation & runbooks; automated ticketing; blameless postmortems

## Key Metrics
- MTTR; alert fatigue (noise vs actionable); SLO compliance %
- Coverage: % services with metrics, logs, tracing enabled
