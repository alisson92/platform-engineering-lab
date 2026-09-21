# Official sources matrix

Status: approved
Owner: platform engineering
Source: [EP00 — Governance and project foundations](../architecture/platform-engineering-lab-architecture-v0.1.md) (section 27), sections 34–35

This matrix consolidates, in a reusable tabular form, the references already listed in prose in sections 34 (normative) and 35 (educational) of the architecture document. It does not duplicate them — it adds the traceability columns the prose does not have: the version/date actually consulted, and which section or epic the source supports. Each spike or epic that pins a real version (the "technical lock" mentioned in section 34) must update the "version/date consulted" column here.

## Normative sources

| Topic | Official source | Link | Version/date consulted | Supports (section/EP) | Type |
|---|---|---|---|---|---|
| Camunda licensing | Camunda 8 — Licensing | https://docs.camunda.io/docs/reference/licenses/ | not yet pinned | §6, EP01 | normative |
| Camunda Helm deployment | Camunda 8 Self-Managed — Helm | https://docs.camunda.io/docs/self-managed/deployment/helm/ | not yet pinned | §12, EP08 | normative |
| Camunda version matrix | Camunda 8 — Version matrix | https://docs.camunda.io/docs/reference/supported-environments/ | not yet pinned | §12, EP01 | normative |
| Camunda production architecture | Camunda 8 — Production architecture | https://docs.camunda.io/docs/self-managed/reference-architecture/ | not yet pinned | §9, §12 | normative |
| EKS | Amazon EKS User Guide | https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html | not yet pinned | §10, EP01/EP03 | normative |
| EKS access entries | EKS access entries | https://docs.aws.amazon.com/eks/latest/userguide/access-entries.html | not yet pinned | §17.2, EP05 | normative |
| EKS Pod Identity | EKS Pod Identity | https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html | not yet pinned | §17.3, EP05 | normative |
| Ingress | AWS Load Balancer Controller | https://kubernetes-sigs.github.io/aws-load-balancer-controller/latest/ | not yet pinned | §19, EP01/EP04 | normative |
| Autoscaling | Cluster Autoscaler on AWS | https://docs.aws.amazon.com/eks/latest/best-practices/cas.html | not yet pinned | §10, EP03 | normative |
| Network isolation | Kubernetes Network Policies | https://kubernetes.io/docs/concepts/services-networking/network-policies/ | not yet pinned | §11, EP04/EP06 | normative |
| Access control | Kubernetes RBAC | https://kubernetes.io/docs/reference/access-authn-authz/rbac/ | not yet pinned | §17, EP05 | normative |
| GitOps principles | OpenGitOps Principles | https://opengitops.dev/ | not yet pinned | §15, EP04 | normative |
| GitOps engine | Argo CD documentation | https://argo-cd.readthedocs.io/ | not yet pinned | §15, EP04 | normative |
| GitOps operator | Argo CD Operator | https://argocd-operator.readthedocs.io/ | not yet pinned | §15, EP04 | normative |
| CI/CD identity | GitHub Actions — OIDC with AWS | https://docs.github.com/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-aws | not yet pinned | §16.2, §17.3, EP00/EP03 | normative |
| IaC language | Terraform language and modules | https://developer.hashicorp.com/terraform/language | not yet pinned | §22, EP03 | normative |
| IaC EKS module | Terraform AWS EKS module | https://github.com/terraform-aws-modules/terraform-aws-eks | not yet pinned | §10, EP03 | normative |
| Telemetry standard | OpenTelemetry documentation | https://opentelemetry.io/docs/ | not yet pinned | §13, EP07 | normative |
| Telemetry semantics | OpenTelemetry semantic conventions | https://opentelemetry.io/docs/specs/semconv/ | not yet pinned | §13, EP07 | normative |
| Telemetry collection | OpenTelemetry Collector deployment | https://opentelemetry.io/docs/collector/deployment/ | not yet pinned | §13, EP07 | normative |
| Metrics | Prometheus documentation | https://prometheus.io/docs/ | not yet pinned | §13–14, EP07 | normative |
| Alerting | Alertmanager | https://prometheus.io/docs/alerting/latest/alertmanager/ | not yet pinned | §14, EP07 | normative |
| Logs | OpenSearch documentation | https://docs.opensearch.org/ | not yet pinned | §13, EP07 | normative |
| Tracing | Jaeger documentation | https://www.jaegertracing.io/docs/ | not yet pinned | §13, EP07 | normative |
| Dashboards | Perses documentation | https://perses.dev/ | not yet pinned | §14, EP07/EP10 | normative |
| Policy as Code | Kyverno documentation | https://kyverno.io/docs/ | not yet pinned | §18, EP06 | normative |
| Vulnerability scanning | Trivy documentation | https://trivy.dev/latest/docs/ | not yet pinned | §16.3, §18, EP06/EP11 | normative |
| Secrets | External Secrets Operator | https://external-secrets.io/latest/ | not yet pinned | §17.3, §20, EP05 | normative |
| DNS | ExternalDNS | https://kubernetes-sigs.github.io/external-dns/latest/ | not yet pinned | §19, EP04 | normative |
| DNS provider | Cloudflare API tokens | https://developers.cloudflare.com/fundamentals/api/get-started/create-token/ | not yet pinned | §19, EP04 | normative |

## Educational sources (not normative)

Configuration and technical behavior are always checked against the normative sources above, never against these.

| Source | Notes |
|---|---|
| Personal collection `alisson92/platform-engineering-notes` | Covers the eleven completed courses referenced in §26 |
| *Create your own platform reference architecture* (Platform Engineering course) | Contributes principles and vocabulary only |
| Demo repository cited in the *Observability for Platform Engineering* course | Contributes principles and vocabulary only |
