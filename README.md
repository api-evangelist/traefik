# Traefik Labs (traefik)

Traefik Labs builds cloud-native traffic and API infrastructure - the open-source Traefik Proxy (an ingress controller, reverse proxy, and load balancer for Kubernetes, Docker, Nomad, ECS, Consul, and bare metal), plus the commercial Traefik Hub product line covering API Gateway, API Management, AI Gateway, and MCP Gateway. The data plane is the same Traefik binary across every tier; the Hub control plane adds GitOps-driven CRDs, a developer portal, multi-cluster dashboards, WAF, advanced auth, and AI safety / agent-governance capabilities.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/traefik/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/traefik/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- AI Gateway
- API Gateway
- API Management
- Developer Portal
- GitOps
- Kubernetes
- Load Balancer
- MCP Gateway
- Open Source
- Reverse Proxy
- WAF

## Timestamps

- **Created:** 2026-03-18
- **Modified:** 2026-05-19

## APIs

### Traefik Proxy

Traefik Proxy is the flagship open-source (MIT) cloud-native reverse proxy, ingress controller, and load balancer. It auto-discovers services from Kubernetes (Ingress, Gateway API, CRD), Docker, Docker Swarm, Nomad, Amazon ECS, Consul, file, and HTTP providers, and ships with native ACME (Let's Encrypt) certificate provisioning, HTTP/2, HTTP/3, gRPC, WebSockets, TCP, UDP, an extensible middleware chain, and a built-in dashboard.

- **Human URL:** [https://traefik.io/traefik/](https://traefik.io/traefik/)

#### Tags

- API Gateway
- Ingress Controller
- Kubernetes
- Load Balancer
- Open Source
- Reverse Proxy

#### Properties

- [Documentation](https://doc.traefik.io/traefik/)
- [Getting  Started](https://doc.traefik.io/traefik/getting-started/quick-start/)
- [Reference](https://doc.traefik.io/traefik/reference/static-configuration/cli/)
- [Change  Log](https://github.com/traefik/traefik/blob/master/CHANGELOG.md)
- [GitHub Repository](https://github.com/traefik/traefik)
- [License](https://github.com/traefik/traefik/blob/master/LICENSE.md)
- [Helm  Chart](https://github.com/traefik/traefik-helm-chart)
- [Docker  Image](https://hub.docker.com/_/traefik)
- [Plugin  Catalog](https://plugins.traefik.io/)
- [Kubernetes C R D](crd/traefik-ingressroute.yaml)
- [Kubernetes C R D](crd/traefik-ingressroutetcp.yaml)
- [Kubernetes C R D](crd/traefik-ingressrouteudp.yaml)
- [Kubernetes C R D](crd/traefik-middleware.yaml)
- [Kubernetes C R D](crd/traefik-middlewaretcp.yaml)
- [Kubernetes C R D](crd/traefik-tlsoption.yaml)
- [Kubernetes C R D](crd/traefik-tlsstore.yaml)
- [Kubernetes C R D](crd/traefik-traefikservice.yaml)
- [Kubernetes C R D](crd/traefik-serverstransport.yaml)
- [Kubernetes C R D](crd/traefik-serverstransporttcp.yaml)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Proxy REST API

The Traefik Proxy REST API exposes runtime configuration and state for every router, service, middleware, and entry point in a running Traefik instance, plus version metadata, raw dynamic configuration, and an anonymized support-dump archive for vendor troubleshooting. Read-only; must be enabled in static configuration and gated behind auth before being exposed.

- **Human URL:** [https://doc.traefik.io/traefik/reference/install-configuration/api-dashboard/](https://doc.traefik.io/traefik/reference/install-configuration/api-dashboard/)
- **Base URL:** `http://localhost:8080/api`

#### Tags

- Configuration
- Management
- Observability
- REST

#### Properties

- [Documentation](https://doc.traefik.io/traefik/reference/install-configuration/api-dashboard/)
- [OpenAPI](openapi/traefik-proxy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Spectral Rules](rules/traefik-proxy-rules.yml) — [Spectral](https://docs.stoplight.io/docs/spectral)
- [Capability](capabilities/shared/traefik-proxy.yaml)
- [Capability](capabilities/gateway-operations.yaml)
- [Capability](capabilities/traffic-observability.yaml)

### Traefik Ping API

Lightweight liveness probe at `/ping` that returns HTTP 200 with body "OK" when the Traefik process is alive. Usually mounted on a dedicated entry point for container-orchestrator liveness checks.

- **Human URL:** [https://doc.traefik.io/traefik/operations/ping/](https://doc.traefik.io/traefik/operations/ping/)

#### Tags

- Health Check
- Liveness
- Monitoring
- Operations

#### Properties

- [Documentation](https://doc.traefik.io/traefik/operations/ping/)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Dashboard

Built-in single-page web UI rendering routers, services, middlewares, entry points, providers, version, and TLS configuration in real time. Shares the API handler; exposed at `/dashboard/` (trailing slash required).

- **Human URL:** [https://doc.traefik.io/traefik/operations/dashboard/](https://doc.traefik.io/traefik/operations/dashboard/)

#### Tags

- Dashboard
- Management
- Observability
- UI

#### Properties

- [Documentation](https://doc.traefik.io/traefik/operations/dashboard/)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Hub API Gateway

Commercial Kubernetes-native API gateway built on Traefik Proxy. Adds a native WAF (claimed 23x faster than alternatives), advanced authentication (LDAP, JWT, HMAC, OAuth2, OIDC, OPA), HashiCorp Vault integration, distributed Let's Encrypt, multi-cluster management, and FIPS 140-2 compliance. Pricing is contract-based; a 30-day free trial is offered.

- **Human URL:** [https://traefik.io/traefik-hub-api-gateway/](https://traefik.io/traefik-hub-api-gateway/)

#### Tags

- API Gateway
- Enterprise
- Kubernetes
- WAF

#### Properties

- [Documentation](https://doc.traefik.io/traefik-hub/)
- [Pricing](https://traefik.io/pricing/)
- [Plans](plans/traefik-plans-pricing.yml)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Hub API Management

Kubernetes-native API management on top of the Hub API Gateway. Surfaces a declarative CRD set - API, APIVersion, APIBundle, APIPlan, APIPortal, APICatalogItem, ManagedSubscription - plus a multi-cluster developer portal, OpenAPI rendering, GitOps configuration linter, and built-in identity provider integration.

- **Human URL:** [https://traefik.io/traefik-hub/](https://traefik.io/traefik-hub/)

#### Tags

- API Management
- Developer Portal
- GitOps
- Kubernetes

#### Properties

- [Documentation](https://doc.traefik.io/traefik-hub/)
- [Reference](https://doc.traefik.io/traefik-hub/api-management/api-plans)
- [Pricing](https://traefik.io/pricing/)
- [Kubernetes C R D](crd/hub-api.yaml)
- [Kubernetes C R D](crd/hub-apiversion.yaml)
- [Kubernetes C R D](crd/hub-apibundle.yaml)
- [Kubernetes C R D](crd/hub-apiplan.yaml)
- [Kubernetes C R D](crd/hub-apiportal.yaml)
- [Kubernetes C R D](crd/hub-apicatalogitem.yaml)
- [Kubernetes C R D](crd/hub-managedsubscription.yaml)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik AI Gateway

Self-hosted Kubernetes-native gateway for LLM traffic. OpenAI-compatible unified API in front of OpenAI, Anthropic, Azure OpenAI, AWS Bedrock, Cohere, Gemini, Mistral, Ollama, and self-hosted models. Built-in jailbreak detection (NVIDIA Safety NIMs), PII redaction (Presidio, 35+ recognizers), 22+ content-filter categories, semantic caching (vendor-claimed 40-70% cost reduction), identity-based routing, and OpenTelemetry token/cost metrics.

- **Human URL:** [https://traefik.io/solutions/ai-gateway/](https://traefik.io/solutions/ai-gateway/)

#### Tags

- AI Gateway
- LLM
- Guardrails
- Observability
- Enterprise

#### Properties

- [Solution  Page](https://traefik.io/solutions/ai-gateway/)
- [Kubernetes C R D](crd/hub-aiservice.yaml)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik MCP Gateway

Gateway add-on that governs how AI agents access Model Context Protocol (MCP) servers. Provides identity-aware routing, capability scoping, and audit logging for agent-to-MCP traffic.

- **Human URL:** [https://traefik.io/solutions/mcp-gateway/](https://traefik.io/solutions/mcp-gateway/)

#### Tags

- MCP
- Agent Governance
- Enterprise

#### Properties

- [Solution  Page](https://traefik.io/solutions/mcp-gateway/)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Plugin Catalog

Public registry of community-built Traefik middlewares. Plugins are authored in Go (loaded at runtime through Yaegi without recompiling Traefik) or in WebAssembly. Surfaces categories such as auth, observability, request transformation, security, and providers.

- **Human URL:** [https://plugins.traefik.io/](https://plugins.traefik.io/)

#### Tags

- Plugins
- Extensibility
- Community

#### Properties

- [Catalog  Site](https://plugins.traefik.io/)
- [Git Hub  Topic](https://github.com/topics/traefik-plugin)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Yaegi (Go Interpreter)

Embeddable Go interpreter maintained by Traefik Labs. Powers the Traefik plugin system - plugins are uploaded as Go source and executed at runtime without recompiling Traefik. Also usable standalone as an embeddable scripting layer.

- **Human URL:** [https://github.com/traefik/yaegi](https://github.com/traefik/yaegi)

#### Tags

- Go
- Interpreter
- Plugin Runtime
- Open Source

#### Properties

- [GitHub Repository](https://github.com/traefik/yaegi)
- [License](https://github.com/traefik/yaegi/blob/master/LICENSE)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Traefik Mesh

Lightweight service mesh built on Traefik Proxy. Offers traffic management and observability for service-to-service communication inside a Kubernetes cluster.

- **Human URL:** [https://traefik.io/traefik-mesh/](https://traefik.io/traefik-mesh/)

#### Tags

- Service Mesh
- Kubernetes
- Open Source

#### Properties

- [GitHub Repository](https://github.com/traefik/mesh)
- [Postman Collection](collections/traefik-proxy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/traefik-proxy.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/traefik)
- [Website](https://traefik.io/)
- [Documentation](https://doc.traefik.io/traefik/)
- [Getting  Started](https://doc.traefik.io/traefik/getting-started/quick-start/)
- [Pricing](https://traefik.io/pricing/)
- [Blog](https://traefik.io/blog/)
- [Change  Log](https://github.com/traefik/traefik/blob/master/CHANGELOG.md)
- [Git Hub  Organization](https://github.com/traefik)
- [GitHub Repository](https://github.com/traefik/traefik)
- [Issue  Tracker](https://github.com/traefik/traefik/issues)
- [Community](https://community.traefik.io/)
- [Stack  Overflow](https://stackoverflow.com/questions/tagged/traefik)
- [Plugin  Catalog](https://plugins.traefik.io/)
- [Helm  Chart](https://github.com/traefik/traefik-helm-chart)
- [Integrations](https://traefik.io/partners)
- [J S O N- L D](json-ld/traefik-context.jsonld)
- [JSON Schema](json-schema/traefik-router-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/traefik-service-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/traefik-middleware-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/traefik-entrypoint-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/traefik-router-structure.json)
- [JSON Structure](json-structure/traefik-middleware-structure.json)
- [Vocabulary](vocabulary/traefik-vocabulary.yml)
- [Spectral Rules](rules/traefik-proxy-rules.yml) — [Spectral](https://docs.stoplight.io/docs/spectral)
- [Plans](plans/traefik-plans-pricing.yml)
- [Rate Limits](rate-limits/traefik-rate-limits.yml)
- [Fin Ops](finops/traefik-finops.yml)
- [L L Ms Txt](https://traefik.io/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
