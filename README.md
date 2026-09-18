# MCP Local Server Development Commands

-  Run the MCP server:
```bash
uv run fastmcp run Server/local_server.py
```

- Run MCP server with inspector for development and testing:
```bash
uv run fastmcp dev inspector Server/local_server.py
```

- Add MCP server to claude-desktop connectors:
```bash
uv run fastmcp install claude-desktop Server/local_server.py
```