# Installing tossithere for an AI agent

tossithere is a hosted MCP server. There is nothing to download, build or run.

1. Add a remote MCP server named `tossithere` with the URL `https://tossithere.com/mcp`
   and the Streamable HTTP transport. For clients that take JSON:

   ```json
   {
     "mcpServers": {
       "tossithere": { "type": "streamableHttp", "url": "https://tossithere.com/mcp" }
     }
   }
   ```

2. Sign in. The server answers the first request with 401 and points the client at
   its OAuth metadata (OAuth 2.1, PKCE, dynamic client registration). The user signs
   in to tossithere in the browser and chooses Allow.

   If the client can't do OAuth, the user creates an API key at
   https://tossithere.com/keys and the client sends it as a header:
   `Authorization: Bearer toss_sk_...`

3. Check it worked: the server lists 8 tools, starting with `publish_page`. Publish a
   one-line HTML page and open the link it returns.

Setup guides for each app: https://tossithere.com/mcp
