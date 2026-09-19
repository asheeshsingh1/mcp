## Types of Connections:
* Config Files
* Direct Connectors or built-in plugins.

## What are Connectors:
* A Connector is a built-in feature that links Claude to MCP servers automatically, without the need for manual setup or configuration.
* Most Claude Desktop users are non-technical end-users who just want Claude to
"talk" to their apps (Notion, Google Drive, GitHub, Slack, etc.).
* They don't want to run servers, edit JSON, or worry about transports.
* The Connector system wraps an MCP server behind the scenes and handles authentication via OAuth (sign-in with Google, GitHub, etc.).
* This keeps things easy, safe, and consistent.
* Think of Connectors as the "App Store" for MCP servers - user-friendly, click-based, pre-curated.

## Why not use Connectors always?
* Connectors Are ``Curated & Managed``
    * Connectors are officially built, hosted, and maintained by Anthropic
    * They come with Auth login flows, managed security, rate-limits, and guaranteed stability.
    * If every MCP server were required to be a Connector, it would mean Anthropic has to review, host, and secure every possible server - which doesn't scale
* MCP is an ``Open Standard``
    * MCP is designed so anyone can write a server
    * Forcing everything through Connectors would ``close the ecosystem`` and make you dependent on Anthropic to approve or publish servers.