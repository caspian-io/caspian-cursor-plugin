# Caspian for Cursor

Caspian is the IT and security system of record for a company's SaaS estate. This plugin connects
Cursor to your Caspian workspace over the remote MCP endpoint `https://app.getcaspian.io/mcp`.

Ask, in plain words, which applications exist, who can access them, what they cost, which devices
are enrolled and which rules are broken. Answers come from the data Caspian already discovered from
the identity provider, connectors, endpoint agents and invoices.

## Install

1. Install this plugin from the Cursor Marketplace, or add the server by hand in **Customize > MCP**
   with the URL `https://app.getcaspian.io/mcp`.
2. Cursor opens the Caspian sign-in page. Sign in to your Caspian workspace and approve the requested
   access.
3. Start a chat and ask a question, for example: `Use Caspian to list the apps we own and who can
   access them.`

## Authentication

OAuth 2.1 with PKCE. Cursor registers itself dynamically (or uses a client metadata document), so no
API key or secret is needed. Scopes:

- `caspian:read` reads apps, people, access, policy violations, vendors, devices and workflows.
- `caspian:write` makes the changes a signed-in admin is allowed to make. Cursor says what will
  change and waits for your agreement; removals ask a second time.

The assistant acts as the signed-in person and never exceeds that person's Caspian role. Each
workspace is explicit: list them, then switch, and every answer names the workspace it came from.

## Requirements

- A Caspian workspace with at least one connected identity provider.
- The Caspian endpoint agent for device questions.
- A workspace Owner or Admin for write tools.

## Links

- Product and documentation: https://getcaspian.io
- Support: support@getcaspian.io
- Privacy policy: https://getcaspian.io/privacy
- Terms of service: https://getcaspian.io/terms

## License

MIT. See [LICENSE](LICENSE).
