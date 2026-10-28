# Dallars Backend & Contracts (dallars-backend)

This repository contains the backend microservices, infrastructure, and Soroban smart contracts for the **Dallars** platform.

## Layout

- `services/`: Fastify microservices
  - `all-in-one`: Unified local dev & deployment bundle
  - `api-gateway`: Ingress, reverse proxy, and rate limiting
  - `lifecycle-service`: Session tracking & lifecycle events
  - `permission-service`: Origin validation and permissions facade
  - `policy-service`: Soroban account policy management & deployment
  - `verification-service`: Trust signals & contract verification
  - `wallet-service`: Account creation, sessions, and relayer submission
  - `worker-service`: Background queues and scheduled tasks
- `contracts/`: Soroban smart contracts (Rust)
  - `attestation-registry`: Contract verification attestations
  - `policy-templates`: Account policy enforcement templates
  - `threshold-attestor`: Multi-sig & threshold attestation verification
- `packages/`:
  - `service-kit`: Shared Fastify and Drizzle/Postgres database tooling
  - `types`: Core domain types
  - `provider-sdk`: Permission validation utilities
- `infra/`: Docker Compose, nginx, and deployment manifests

## Getting Started

```sh
pnpm install
pnpm build
```

## Running Locally

1. Start Postgres & Redis:
   ```sh
   docker compose -f infra/docker/docker-compose.yml up -d
   ```
2. Start the backend services:
   ```sh
   pnpm dev
   ```

## License

Apache-2.0 — see [LICENSE](LICENSE).
