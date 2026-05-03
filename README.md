# Traefik

Traefik is a modern open-source HTTP reverse proxy and load balancer that makes deploying microservices and API gateways easy with automatic service discovery, Let's Encrypt integration, and a rich middleware ecosystem.

**Website:** https://traefik.io/  
**Documentation:** https://doc.traefik.io/traefik/  
**GitHub:** https://github.com/traefik/traefik  
**Community:** https://community.traefik.io/

## APIs

### Traefik Proxy

The core Traefik reverse proxy and load balancer with native Kubernetes, Docker, and cloud provider integration.

- **Documentation:** https://doc.traefik.io/traefik/
- **Getting Started:** https://doc.traefik.io/traefik/getting-started/quick-start/

### Traefik REST API

The Traefik REST API exposes runtime configuration and state for all routers, services, middlewares, and entry points in a running Traefik instance.

- **Documentation:** https://doc.traefik.io/traefik/operations/api/
- **OpenAPI:** [openapi/traefik-api-openapi.yml](openapi/traefik-api-openapi.yml)

### Traefik Ping API

A simple health check endpoint at `/ping` returning HTTP 200 when Traefik is alive.

- **Documentation:** https://doc.traefik.io/traefik/operations/ping/

### Traefik Dashboard

Built-in web UI for visualizing routers, services, and middleware configuration in real time.

- **Documentation:** https://doc.traefik.io/traefik/operations/dashboard/

## Artifacts

### OpenAPI Specs

| Spec | Description |
|------|-------------|
| [traefik-api-openapi.yml](openapi/traefik-api-openapi.yml) | Traefik REST API — routers, services, middlewares, entry points, health |

### Spectral Rules

| File | Description |
|------|-------------|
| [traefik-api-rules.yml](rules/traefik-api-rules.yml) | Spectral ruleset enforcing Traefik API conventions |

### Naftiko Capabilities

#### Shared Definitions

| File | Description |
|------|-------------|
| [shared/traefik-api.yaml](capabilities/shared/traefik-api.yaml) | Per-API consumed definition for the Traefik REST API |

#### Workflow Capabilities

| File | Description |
|------|-------------|
| [proxy-operations.yaml](capabilities/proxy-operations.yaml) | Proxy operations — routing inspection, health monitoring, configuration (10 tools) |

### JSON Schemas

| File | Description |
|------|-------------|
| [traefik-router-schema.json](json-schema/traefik-router-schema.json) | Schema for HTTP router configuration |
| [traefik-service-schema.json](json-schema/traefik-service-schema.json) | Schema for HTTP service configuration |

### JSON Structure

| File | Description |
|------|-------------|
| [traefik-router-structure.json](json-structure/traefik-router-structure.json) | Structure documentation for HTTP Router objects |

### JSON-LD

| File | Description |
|------|-------------|
| [traefik-context.jsonld](json-ld/traefik-context.jsonld) | JSON-LD context for Traefik linked data semantics |

### Examples

| File | Description |
|------|-------------|
| [traefik-get-version-example.json](examples/traefik-get-version-example.json) | Example response for GET /version |
| [traefik-list-http-routers-example.json](examples/traefik-list-http-routers-example.json) | Example response for GET /http/routers |

### Vocabulary

| File | Description |
|------|-------------|
| [traefik-vocabulary.yml](vocabulary/traefik-vocabulary.yml) | Domain vocabulary for Traefik routing concepts |

## Maintainers

- **Kin Lane** (kin@apievangelist.com)
