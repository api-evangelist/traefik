# Traefik Labs

Traefik Labs builds cloud-native traffic and API infrastructure: the open-source **Traefik Proxy** reverse proxy / ingress controller / load balancer, plus the commercial **Traefik Hub** product line (API Gateway, API Management, AI Gateway, MCP Gateway). The same Traefik binary powers every tier; Hub adds a GitOps control plane, developer portal, multi-cluster dashboard, WAF, advanced auth, and AI/agent governance.

- **Website:** https://traefik.io/
- **Documentation:** https://doc.traefik.io/traefik/
- **GitHub:** https://github.com/traefik
- **Community:** https://community.traefik.io/
- **Plugin Catalog:** https://plugins.traefik.io/

## Products and APIs

### Traefik Proxy (Open Source, MIT)

Cloud-native reverse proxy, ingress controller, and load balancer. Native Kubernetes / Docker / Nomad / ECS / Consul / file provider auto-discovery, Let's Encrypt, HTTP/2/3, gRPC, WebSockets, TCP, UDP, 25+ HTTP middlewares, a built-in dashboard, and a runtime plugin system (Yaegi + WebAssembly).

- **Repo:** https://github.com/traefik/traefik
- **Docs:** https://doc.traefik.io/traefik/

### Traefik Proxy REST API

Read-only HTTP control surface for inspecting routers, services, middlewares, entry points, raw dynamic configuration, version, and the anonymized support-dump archive.

- **Docs:** https://doc.traefik.io/traefik/reference/install-configuration/api-dashboard/
- **OpenAPI:** [openapi/traefik-proxy-openapi.yml](openapi/traefik-proxy-openapi.yml)

### Traefik Hub API Gateway (Commercial)

Enterprise-grade API gateway built on Traefik Proxy. Adds native WAF, LDAP / JWT / OAuth2 / OIDC / OPA / HMAC, HashiCorp Vault integration, distributed Let's Encrypt, multi-cluster management, and FIPS 140-2 compliance.

- **Page:** https://traefik.io/traefik-hub-api-gateway/

### Traefik Hub API Management (Commercial)

Kubernetes-native API management on top of the Hub Gateway. Declarative CRD model (`API`, `APIVersion`, `APIBundle`, `APIPlan`, `APIPortal`, `APICatalogItem`, `ManagedSubscription`) plus a multi-cluster developer portal, OpenAPI rendering, GitOps configuration linter, and built-in IdP.

- **Page:** https://traefik.io/traefik-hub/
- **Docs:** https://doc.traefik.io/traefik-hub/

### Traefik AI Gateway (Commercial Add-On)

OpenAI-compatible unified API in front of OpenAI / Anthropic / Azure OpenAI / AWS Bedrock / Cohere / Gemini / Mistral / Ollama / self-hosted models. Built-in jailbreak detection (NVIDIA Safety NIMs), PII redaction (Presidio), 22+ content-filter categories, semantic caching, and OpenTelemetry token/cost metrics.

- **Page:** https://traefik.io/solutions/ai-gateway/

### Traefik MCP Gateway (Commercial Add-On)

Governs how AI agents access Model Context Protocol servers - identity-aware routing, capability scoping, audit logging.

- **Page:** https://traefik.io/solutions/mcp-gateway/

### Traefik Plugin Catalog

Public registry of community Traefik middlewares written in Go (Yaegi-interpreted) or WebAssembly.

- **Catalog:** https://plugins.traefik.io/

### Yaegi

Embeddable Go interpreter maintained by Traefik Labs; powers the Traefik plugin loader.

- **Repo:** https://github.com/traefik/yaegi

### Traefik Mesh

Lightweight Traefik-based service mesh for Kubernetes.

- **Repo:** https://github.com/traefik/mesh

## Artifacts

### OpenAPI

| Spec | Description |
|---|---|
| [traefik-proxy-openapi.yml](openapi/traefik-proxy-openapi.yml) | Traefik Proxy REST API - routers, services, middlewares, entry points, overview, raw data, support dump, version, ping. |

### Spectral Rules

| File | Description |
|---|---|
| [traefik-proxy-rules.yml](rules/traefik-proxy-rules.yml) | Spectral ruleset enforcing Traefik API conventions (info/version, title-case summaries, tags, response shape). |

### Naftiko Capabilities

| File | Description |
|---|---|
| [shared/traefik-proxy.yaml](capabilities/shared/traefik-proxy.yaml) | Per-API consumed definition for the full Traefik Proxy REST surface. |
| [gateway-operations.yaml](capabilities/gateway-operations.yaml) | Workflow capability for inspecting routers, services, and middlewares (HTTP / TCP / UDP). |
| [traffic-observability.yaml](capabilities/traffic-observability.yaml) | Workflow capability for version, overview, entry-point inspection, and ping/support-dump. |

### Kubernetes CRDs

Traefik Proxy (`traefik.io/v1alpha1`):

| File | Kind | Purpose |
|---|---|---|
| [crd/traefik-ingressroute.yaml](crd/traefik-ingressroute.yaml) | `IngressRoute` | HTTP routing. |
| [crd/traefik-ingressroutetcp.yaml](crd/traefik-ingressroutetcp.yaml) | `IngressRouteTCP` | TCP routing (HostSNI). |
| [crd/traefik-ingressrouteudp.yaml](crd/traefik-ingressrouteudp.yaml) | `IngressRouteUDP` | UDP routing. |
| [crd/traefik-middleware.yaml](crd/traefik-middleware.yaml) | `Middleware` | HTTP middleware (25+ types). |
| [crd/traefik-middlewaretcp.yaml](crd/traefik-middlewaretcp.yaml) | `MiddlewareTCP` | TCP middleware (IP allow-list, in-flight conn). |
| [crd/traefik-tlsoption.yaml](crd/traefik-tlsoption.yaml) | `TLSOption` | Reusable TLS parameters. |
| [crd/traefik-tlsstore.yaml](crd/traefik-tlsstore.yaml) | `TLSStore` | Default TLS certificate store. |
| [crd/traefik-traefikservice.yaml](crd/traefik-traefikservice.yaml) | `TraefikService` | Weighted / mirroring service composition. |
| [crd/traefik-serverstransport.yaml](crd/traefik-serverstransport.yaml) | `ServersTransport` | HTTP backend transport (TLS, idle conn). |
| [crd/traefik-serverstransporttcp.yaml](crd/traefik-serverstransporttcp.yaml) | `ServersTransportTCP` | TCP backend transport. |

Traefik Hub (`hub.traefik.io/v1alpha1`):

| File | Kind | Purpose |
|---|---|---|
| [crd/hub-api.yaml](crd/hub-api.yaml) | `API` | Hub-managed API resource. |
| [crd/hub-apiversion.yaml](crd/hub-apiversion.yaml) | `APIVersion` | API version with lifecycle stage. |
| [crd/hub-apibundle.yaml](crd/hub-apibundle.yaml) | `APIBundle` | Subscribable API group. |
| [crd/hub-apiplan.yaml](crd/hub-apiplan.yaml) | `APIPlan` | Rate limit + quota policy. |
| [crd/hub-apiportal.yaml](crd/hub-apiportal.yaml) | `APIPortal` | Developer portal. |
| [crd/hub-apicatalogitem.yaml](crd/hub-apicatalogitem.yaml) | `APICatalogItem` | Portal visibility scope. |
| [crd/hub-managedsubscription.yaml](crd/hub-managedsubscription.yaml) | `ManagedSubscription` | Runtime authorization binding. |
| [crd/hub-aiservice.yaml](crd/hub-aiservice.yaml) | `AIService` | AI Gateway LLM upstream + guardrails. |

### JSON Schemas

| File | Description |
|---|---|
| [traefik-router-schema.json](json-schema/traefik-router-schema.json) | HTTP/TCP/UDP router. |
| [traefik-service-schema.json](json-schema/traefik-service-schema.json) | Backend service. |
| [traefik-middleware-schema.json](json-schema/traefik-middleware-schema.json) | HTTP middleware. |
| [traefik-entrypoint-schema.json](json-schema/traefik-entrypoint-schema.json) | Network entry point. |

### JSON Structure

| File | Description |
|---|---|
| [traefik-router-structure.json](json-structure/traefik-router-structure.json) | HTTP router. |
| [traefik-middleware-structure.json](json-structure/traefik-middleware-structure.json) | HTTP middleware. |

### JSON-LD

| File | Description |
|---|---|
| [traefik-context.jsonld](json-ld/traefik-context.jsonld) | Router, Service, Middleware, EntryPoint, LoadBalancer, Server, TLSConfig, Version, Overview. |

### Examples

| File | Description |
|---|---|
| [traefik-get-version-example.json](examples/traefik-get-version-example.json) | `GET /api/version`. |
| [traefik-get-overview-example.json](examples/traefik-get-overview-example.json) | `GET /api/overview`. |
| [traefik-list-entrypoints-example.json](examples/traefik-list-entrypoints-example.json) | `GET /api/entrypoints`. |
| [traefik-list-http-routers-example.json](examples/traefik-list-http-routers-example.json) | `GET /api/http/routers`. |
| [traefik-list-http-services-example.json](examples/traefik-list-http-services-example.json) | `GET /api/http/services`. |
| [traefik-list-http-middlewares-example.json](examples/traefik-list-http-middlewares-example.json) | `GET /api/http/middlewares`. |

### Plans, Rate Limits, FinOps

| File | Description |
|---|---|
| [traefik-plans-pricing.yml](plans/traefik-plans-pricing.yml) | API Commons Plans 0.1 - 5 plans (OSS Proxy + 4 commercial tiers). |
| [traefik-rate-limits.yml](rate-limits/traefik-rate-limits.yml) | API Commons Rate Limits 0.1 - operator-configured middlewares + Hub APIPlan. |
| [traefik-finops.yml](finops/traefik-finops.yml) | FOCUS 1.3 / FinOps Framework 1.0 - subscription, clusters, seats, managed APIs, AI tokens, infra meters. |

### Vocabulary

| File | Description |
|---|---|
| [traefik-vocabulary.yml](vocabulary/traefik-vocabulary.yml) | Routing concepts plus Hub CRDs, AI Gateway, MCP Gateway, plugin runtime terms. |

## Maintainers

- **Kin Lane** (kin@apievangelist.com)
