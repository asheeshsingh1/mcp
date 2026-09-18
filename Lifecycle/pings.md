## Pings

Ping is a lightweight request/response method defined in MCP.
- Purpose: to check whether the other side (Host or Server) is still alive and the connection is responsive.

    Ping:

        {
            "jsonrpc": "2.0",
            "id": 42,
            "method": "ping"
        }

    Response:

        
        {
            "¡sonrpc": "2.0", 
            "id": 42, 
            "result": {} 
        }

## When is Ping used?
- Useful for checking if the other side is up before full initialize.
- If there's no activity for a while, a client may send periodic pings.
- Prevents the connection from being dropped silently by the OS, proxies, or firewalls.