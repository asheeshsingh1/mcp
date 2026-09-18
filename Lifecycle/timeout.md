# Timeout, Cancellation and Progress Notification

Ensures requests don't hang forever.

## Purpose
- Protects against unresponsive or overloaded servers.
- Ensures resources (memory, CPU)
aren't held indefinitely.
- Gives the user feedback instead of waiting forever.

## How Timeout Works
- SDKs let Client sets a per-request timeout (e.g., 30s).
- If the deadline passes with no result → client triggers a timeout.
- Client then sends a cancellation notification to tell the server to stop.
- The server must stop processing that request and not return a result.


## Cancellation

Request Sent:

        {
            "jsonrpc": "2.0",
            "id": "7"
            "method": "tools/call",
            "params": {
                "name": "searchCode"
                "arguments": {
                    "query": "MCP"
                },
                "_meta": {
                    "progressToken": "tok-7"
                }
            }
        }

Cancel Request:

        {
            "jsonrpc": "2.0"
            "method": "notifications/cancelled",
            "params": {
                "requestId": "7",
                "reason": "Timeout exceeded (30s)"
            }
        }

## Progress Notification
- Purpose: Let the client know a long-running request is still making progress.
- Client includes a progressToken in the request's _meta.
- Server can then send notifications/progress updates while working.

Request sent by client:

        {
            "jsonrpc"
            : "2.0",
            "id": 7,
            "method": "tools/call",
            "params": {
                "name": "searchCode",
                "arguments": {
                    "query": "MCP lifecycle"
                },
                "_meta": {
                    "progressToken": "tok-7"
                }
            }
        }

Notification sent by server:

        {
            "jsonrpc": "2.0",
            "method": "notifications/progress",
            "params": {
                "progressToken": "tok-7",
                "progress": 60,
                "total": 100,
                "message": "Searching 600 of 1000 files"
            }
        }