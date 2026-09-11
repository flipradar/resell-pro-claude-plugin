# Resell Pro connection setup

The package configures the Resell Pro remote MCP server at
`https://resellpro.com/mcp`. When your client asks to connect, use the standard
OAuth authorization flow in the browser.

1. Open the authorization page that your client presents.
2. Sign in to Resell Pro or create an account at
   [resellpro.com](https://resellpro.com).
3. Review the requested access and approve it only if it is expected.
4. Return to your client and confirm that the `resell-pro` MCP server is
   connected.

Do not ask for, paste, save, or transmit a password, API key, access token,
cookie, OAuth authorization code, or other secret in chat or configuration.
OAuth handles authorization directly with Resell Pro.

If connection fails, retry the normal OAuth flow and contact
[hello@resellpro.com](mailto:hello@resellpro.com). Do not use shell commands,
curl, browser automation, or alternate endpoints to work around authentication.
