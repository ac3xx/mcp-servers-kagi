# kagi-server MCP Server

[![smithery badge](https://smithery.ai/badge/kagi-server)](https://smithery.ai/protocol/kagi-server)
MCP server for Kagi API integration

This is a TypeScript-based MCP server that integrates the Kagi Search API. It demonstrates core MCP concepts by providing:

- Tools for performing web searches and other operations using Kagi's API (currently in private beta)

<a href="https://glama.ai/mcp/servers/z0f3dzmha4"><img width="380" height="200" src="https://glama.ai/mcp/servers/z0f3dzmha4/badge" alt="Kagi server MCP server" /></a>

## Features

### Implemented Tools
- `kagi_search` - Perform web searches using Kagi
  - Takes a query string and optional limit as parameters
  - Returns search results from Kagi's API

### Planned Tools (Not Yet Implemented)
- `kagi_summarize` - Generate summaries of web pages or text
- `kagi_fastgpt` - Get quick responses using Kagi's FastGPT
- `kagi_enrich` - Fetch enriched news results on specific topics

## Development

Install dependencies:
```bash
npm install
```

Build the server:
```bash
npm run build
```

For development with auto-rebuild:
```bash
npm run watch
```

## Environment Setup

Create a `.env` file in the root directory with your Kagi API key:

```
KAGI_API_KEY=your_api_key_here
```

Make sure to add `.env` to your `.gitignore` file to keep your API key secure.

## Installation

### Installing via Smithery

To install Kagi Server for Claude Desktop automatically via [Smithery](https://smithery.ai/protocol/kagi-server):

```bash
npx @smithery/cli install kagi-server --client claude
```

To use with Claude Desktop, add the server config:

On MacOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
On Windows: `%APPDATA%/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "kagi-server": {
      "command": "/path/to/kagi-server/build/index.js",
      "env": {
        "KAGI_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

### Debugging

Since MCP servers communicate over stdio, debugging can be challenging. We recommend using the [MCP Inspector](https://github.com/modelcontextprotocol/inspector), which is available as a package script:

```bash
npm run inspector
```

The Inspector will provide a URL to access debugging tools in your browser.

## Usage

Once the server is running and connected to Claude Desktop, you can use it to perform web searches. For example:

1. Ask Claude: "Can you search for information about the latest advancements in quantum computing?"
2. Claude will use the `kagi_search` tool to fetch results from Kagi's API.
3. Claude will then summarize or analyze the search results for you.

Note: The planned tools (summarize, fastgpt, enrich) are not yet implemented and cannot be used.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. Some areas for contribution include:

- Implementing the planned tools (summarize, fastgpt, enrich)
- Improving error handling and input validation
- Enhancing documentation and usage examples

## License

This project is licensed under the MIT License.

## Roadmap

- Implement `kagi_summarize` tool for webpage and text summarization
- Implement `kagi_fastgpt` tool for quick responses
- Implement `kagi_enrich` tool for fetching enriched news results
- Improve error handling and add more robust input validation
- Add more comprehensive usage examples and documentation
- Publish the package to npm for easy installation and use with Claude Desktop and npx
