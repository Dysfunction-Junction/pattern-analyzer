# Agent index

This file is a map. It names checkouts, ports, and the file to open. It does not describe behavior. If a line here and the code disagree, the code wins; then correct this file's path or port.

The launch table is copied from `sovereign-exocortex/apps/daemon/src/mishmash-nodes.ts`. That file is the routing contract. Checkouts sit next to each other. The launcher treats a directory as the repos root when it contains `hermes-api`, `autonomous-triad`, and `pieces-for-all`.

## Family

| Launch id | Directory | Port | Role in the launch table | Mesh entry |
|---|---|---|---|---|
| `exocortexd` | `sovereign-exocortex` | 8788 | gateway | `apps/daemon/src/server.ts` |
| `hermes-api` | `hermes-api` | 3000 | device and phone tasks | `mishmash/delegate.ts` |
| `autonomous-triad` | `autonomous-triad` | 8789 | intent and review | `triad.server` |
| `pieces-for-all` | `pieces-for-all` | 39400 | local memory gateway | `src/server.ts` |
| `agent-mesh-mcp` | `agent-mesh-mcp` | 39401 | local MCP switchboard | `src/mishmash-delegate.ts` |
| `pattern-analyzer` | `pattern-analyzer` | 39402 | pattern lifecycle ranking | `src/mishmash-delegate.ts` |
| `registry-app` | `registry-app` | 39403 | SecondGuess staging | `mishmash/delegate.ts` |
| `gut-instinct` | `Gut-Instinct` | 39404 | on-device coach contract | `mishmash/delegate.mjs` |
| `tool-registry-heartbeat` | `tool-registry-heartbeat` | 39405 | scheduled tool-inventory tasks | `mishmash/delegate.mjs` |

The home proxy (often `:8787`) and PiecesOS (`:39300`) are separate local processes. They are not checkouts in this table.

## This checkout

Mesh launch id `pattern-analyzer`, port 39402, entry [`src/mishmash-delegate.ts`](src/mishmash-delegate.ts). Package name is `@registry/pattern-analyzer`.

| Path | Open when the question is about |
|---|---|
| [`README.md`](README.md) | product overview. The Android clients it names live in other checkouts. |
| [`docs/pattern-analyzer-spec.md`](docs/pattern-analyzer-spec.md) | lifecycle spec. Confirm thresholds in `src/` before treating the spec as implemented. |
| [`src/stateMachine.ts`](src/stateMachine.ts) | lifecycle states |
| [`src/decay.ts`](src/decay.ts) | decay math |
| [`src/pool.ts`](src/pool.ts) | bounded candidate pool |
| [`src/mishmash-rank.ts`](src/mishmash-rank.ts) | ranking used by the mesh delegate |
| [`src/types.ts`](src/types.ts) | shared types |

The Expo client and Cloud Functions are the `registry-app` checkout. The native coach is the `Gut-Instinct` checkout. Desktop inventory tasks are `tool-registry-heartbeat`. This repo is the TypeScript lifecycle engine those call.
