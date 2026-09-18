# MCP Local Server Development Commands

-  Run the MCP server:
```bash
uv run fastmcp run src/my_mcp_server/main.py
```

- Run MCP server with inspector for development and testing:
```bash
uv run fastmcp dev inspector src/my_mcp_server/main.py
```

- Add MCP server to claude-desktop connectors:
```bash
uv run fastmcp install claude-desktop main.py
```