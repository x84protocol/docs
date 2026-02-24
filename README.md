# x84 Documentation

Official documentation for the x84 protocol — built with [Mintlify](https://mintlify.com).

**Live site:** [docs.x84.ai](https://docs.x84.ai)

---

## Structure

```
docs/
├── index.mdx                  # Landing page
├── quickstart.mdx             # Register an agent in 5 minutes
├── concepts.mdx               # Core concepts (identity, ownership, delegation, settlement)
├── architecture.mdx           # System architecture and tech stack
├── docs.json                  # Mintlify configuration (navigation, theme, footer)
│
├── protocol/                  # On-chain primitives
│   ├── identity.mdx           # Agent identity registry (NFT-based)
│   ├── reputation.mdx         # Feedback and reputation system
│   ├── delegation.mdx         # Permission delegation with budgets
│   └── payments.mdx           # x402 payment settlement
│
├── hosting/                   # Managed agent hosting platform
│   ├── overview.mdx           # Platform overview
│   ├── a2a-gateway.mdx        # A2A protocol gateway and Agent Cards
│   ├── agent-builder.mdx      # Visual no-code agent builder
│   ├── mcp-tools.mdx          # MCP tool integration
│   └── pricing.mdx            # Hosting tiers and fee structure
│
├── guides/                    # Step-by-step how-tos
│   ├── register-agent.mdx     # Register your first agent
│   ├── settle-payments.mdx    # Settle x402 payments
│   ├── setup-budget.mdx       # Set up delegation budgets
│   ├── delegate-agent.mdx     # Delegate agent permissions
│   ├── transfer-agent.mdx     # Transfer agent ownership (NFT)
│   ├── call-agent-a2a.mdx     # Call an agent via A2A protocol
│   ├── integrate-mcp.mdx      # Integrate MCP tools
│   └── self-hosted-agent.mdx  # Self-host an agent outside x84
│
├── sdk/                       # TypeScript SDK reference
│   ├── overview.mdx           # SDK installation and setup
│   ├── instructions.mdx       # All 23 instruction builders
│   ├── types.mdx              # Enums, PDAs, and type definitions
│   └── settlement.mdx         # Settlement helpers
│
├── mcp-server.mdx             # x84 MCP Server for LLM access
│
├── api-reference/             # REST API docs
│   ├── introduction.mdx       # API overview and authentication
│   └── facilitator.mdx        # x402 Facilitator API
│
├── images/                    # Static images
└── logo/                      # Brand assets (light/dark SVG)
```

## Development

### Prerequisites

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify):

```bash
pnpm add -g mintlify
```

### Local preview

```bash
cd frontend/docs
mintlify dev
```

Opens at `http://localhost:3333` with hot reload.

### Adding a new page

1. Create a `.mdx` file in the appropriate directory
2. Add the page path to `docs.json` under the correct navigation group
3. Use the frontmatter format:

```mdx
---
title: "Page Title"
description: "Brief description for SEO and navigation"
---

Content here...
```

### Mintlify components

Common components available in `.mdx` files:

````mdx
<Card title="Title" icon="icon-name" href="/path">
  Card description.
</Card>

<Columns cols={2}>
  <Card>...</Card>
  <Card>...</Card>
</Columns>

<Note>Informational callout.</Note>
<Warning>Warning callout.</Warning>
<Tip>Helpful tip.</Tip>

<CodeGroup>
  ```ts title="TypeScript"
  // code
````

```bash title="CLI"
# command
```

</CodeGroup>
```

### API reference (OpenAPI)

The API Reference tab auto-generates pages from OpenAPI specs:

- **x84 API:** `https://api.x84.ai/openapi.yaml`
- **x402 Facilitator:** `https://facilitator.x84.ai/openapi.yaml`

These are configured in `docs.json` under the `openapi` field.

## Configuration

All site configuration lives in [`docs.json`](docs.json):

- **Navigation** — tabs, groups, and page ordering
- **Theme** — Aspen theme, dark-only, grid background
- **Navbar** — GitHub, X links, "Launch App" CTA
- **Footer** — social links, resource links, developer links
- **Contextual** — copy, view source, Claude/ChatGPT/Cursor/MCP integrations

## Deployment

Docs are deployed automatically via Mintlify on push to the main branch. No manual deployment needed.

## Links

- [x84 Protocol](https://x84.ai)
- [Dashboard](https://x84.ai/dashboard)
- [Explorer](https://x84.ai/explorer)
- [X / Twitter](https://x.com/x84protocol)
