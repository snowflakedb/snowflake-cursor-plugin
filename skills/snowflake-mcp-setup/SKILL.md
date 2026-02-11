---
name: snowflake-mcp-setup
description: Guide for setting up and connecting to a Snowflake-managed MCP server from Cursor using Programmatic Access Tokens (PAT)
---

# Snowflake MCP Server Setup

This skill guides you through connecting Cursor to a [Snowflake-managed MCP server](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp), enabling AI agents to securely interact with Snowflake data and services — including Cortex Search, Cortex Analyst, SQL execution, Cortex Agents, and custom tools (UDFs/stored procedures) — directly from the IDE.

## Setup

### 1. Create a Programmatic Access Token (PAT)

Authentication uses a [Programmatic Access Token](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens). Generate one in Snowsight under **Settings → Authentication → Programmatic Access Tokens**. Use the least-privileged role that has USAGE on your MCP server and its tools.

Or with SQL:

```sql
ALTER USER <YOUR_USERNAME> ADD PROGRAMMATIC ACCESS TOKEN <PAT_NAME>;
```

See the [SQL reference](https://docs.snowflake.com/en/sql-reference/sql/alter-user-add-programmatic-access-token) for full details.

### 2. Get Your MCP Server URL

The URL follows this format:

```
https://<account_url>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server_name>
```

Your [account URL](https://docs.snowflake.com/en/user-guide/admin-account-identifier) is typically `<orgname>-<account_name>.snowflakecomputing.com`. Use hyphens (`-`) instead of underscores (`_`) in hostnames. Follow [Snowflake docs](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp) to create an MCP server.

### 3. Configure mcp.json

Replace the placeholder values in `mcp.json` with your MCP server URL and PAT:

```json
{
  "mcpServers": {
    "Snowflake": {
      "url": "<SNOWFLAKE_MCP_SERVER_URL>",
      "headers": {
        "Authorization": "Bearer <SNOWFLAKE_PAT_TOKEN>"
      }
    }
  }
}
```

