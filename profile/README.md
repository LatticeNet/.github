# LatticeNet

LatticeNet builds **Lattice**, a security-first probe, automation, and cluster
network control plane for small fleets.

The project goal is to combine:

- NodeGet-style extensibility and operational UX.
- Nezha-style scoped access control and auditability.
- NodeLite-style conservative defaults and low-risk agent behavior.

## Repositories

- [`latticenet.github.io`](https://github.com/LatticeNet/latticenet.github.io) - public website and documentation entry point.
- [`lattice`](https://github.com/LatticeNet/lattice) - ecosystem overview, roadmap, and local workspace orchestration.
- [`lattice-sdk`](https://github.com/LatticeNet/lattice-sdk) - shared Go models and future protocol definitions.
- [`lattice-server`](https://github.com/LatticeNet/lattice-server) - control plane server.
- [`lattice-node-agent`](https://github.com/LatticeNet/lattice-node-agent) - outbound node agent.
- [`lattice-dashboard`](https://github.com/LatticeNet/lattice-dashboard) - static TypeScript dashboard.
- [`lattice-plugin-template`](https://github.com/LatticeNet/lattice-plugin-template) - starter templates for system, Worker, and Wasm plugins.
- [`lattice-plugin-index`](https://github.com/LatticeNet/lattice-plugin-index) - signed marketplace index foundation.
- [`Astra`](https://github.com/LatticeNet/Astra) - iOS companion app for phone-first fleet operations.

## Install Shape

- `lattice-server`: Docker/Compose or systemd binary behind HTTPS.
- `lattice-node-agent`: systemd host binary by default.
- Container image: `ghcr.io/latticenet/lattice-server`.

## Security Principles

- Agents dial out; nodes do not require public inbound ports.
- Dangerous host changes follow `plan -> review -> approve -> apply`.
- Scopes and server allowlists are mandatory for high-risk operations.
- Plugins cannot bypass the server's authorization and audit layer.
- Public exposure belongs behind WireGuard, Cloudflare Access, nginx/Caddy, or equivalent perimeter controls.

## Status

The project is an early security-first control plane. Private-fleet deployments
should follow the hardening docs, keep management behind HTTPS/WireGuard or
Cloudflare Access, and enable privileged node execution only where reviewed host
mutation is required.
