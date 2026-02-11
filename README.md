# Snowflake Plugin for Cursor

Connect Cursor to Snowflake through the [Snowflake-managed MCP server](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp).

## What's Included

- **MCP Server config** (`mcp.json`) — Pre-configured template for connecting to a Snowflake MCP server using Programmatic Access Tokens (PAT)
- **Setup skill** — Step-by-step instructions for creating a PAT, finding your MCP server URL, and configuring the connection

## Quick Start

1. **Create a Programmatic Access Token** in Snowsight (**Settings → Authentication → Programmatic Access Tokens**) or [via SQL](https://docs.snowflake.com/en/sql-reference/sql/alter-user-add-programmatic-access-token).

2. **Find your MCP server URL** — it follows the format:
   ```
   https://<account_url>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server_name>
   ```

3. **Update `mcp.json`** with your URL and token.

## Capabilities

Once connected, your Cursor agent can use any tools exposed by your Snowflake MCP server:

| Tool Type | Description |
|-----------|-------------|
| Cortex Search | Unstructured search over documents and data |
| Cortex Analyst | Natural language to SQL using semantic views |
| SQL Execution | Run SQL queries directly on Snowflake |
| Cortex Agents | Multi-step agentic workflows |
| Custom Tools | Invoke UDFs and stored procedures |

## Documentation

- [Snowflake-managed MCP server](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp)
- [Programmatic Access Tokens](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens)
- [Account Identifiers](https://docs.snowflake.com/en/user-guide/admin-account-identifier)

## License
Copyright (c) Snowflake Inc. All rights reserved.
Licensed under the Apache 2.0 license.
