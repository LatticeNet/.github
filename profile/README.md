# LatticeNet

LatticeNet builds **Lattice**, a security-first probe, automation, and cluster
network control plane for small fleets.

The project goal is to combine:

- NodeGet-style extensibility and operational UX.
- Nezha-style scoped access control and auditability.
- NodeLite-style conservative defaults and low-risk agent behavior.

## Repositories

- [`lattice`](https://github.com/LatticeNet/lattice) - ecosystem overview, roadmap, and local workspace orchestration.
- [`lattice-sdk`](https://github.com/LatticeNet/lattice-sdk) - shared Go models and future protocol definitions.
- [`lattice-server`](https://github.com/LatticeNet/lattice-server) - control plane server.
- [`lattice-node-agent`](https://github.com/LatticeNet/lattice-node-agent) - outbound node agent.
- [`lattice-dashboard`](https://github.com/LatticeNet/lattice-dashboard) - static TypeScript dashboard.
- [`lattice-plugin-template`](https://github.com/LatticeNet/lattice-plugin-template) - starter templates for system, Worker, and Wasm plugins.

## Security Principles

- Agents dial out; nodes do not require public inbound ports.
- Dangerous host changes follow `plan -> review -> approve -> apply`.
- Scopes and server allowlists are mandatory for high-risk operations.
- Plugins cannot bypass the server's authorization and audit layer.
- Public exposure belongs behind WireGuard, Cloudflare Access, nginx/Caddy, or equivalent perimeter controls.

## Status

The first public cut is an MVP skeleton intended for rapid hardening. Production
deployments should wait for SQLite migrations, packaged releases, and expanded
security review.

