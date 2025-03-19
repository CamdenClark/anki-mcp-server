# anki-mcp MCP Server
[![smithery badge](https://smithery.ai/badge/@CamdenClark/anki-mcp-server)](https://smithery.ai/server/@CamdenClark/anki-mcp-server)

A server to integrate with Anki via the AnkiConnect   plugin

This is a TypeScript-based MCP server that integrates with Anki via the AnkiConnect plugin. It demonstrates core MCP concepts by providing:

- Resources representing Anki decks and note models with URIs
- Tools for creating and managing Anki notes
- Integration with AnkiConnect API

## Features

### Resources
- List and access Anki decks via `anki://decks/{id}` URIs
- List and access note models via `anki://models/{id}` URIs
- JSON representation of Anki objects

### Tools
- `listDecks` - Get names of all decks
- `listModels` - Get names of all note models
- `getModel` - Get details of a specific note model
- `addNote` - Create a single note
  - Specify deck name, model name, fields and tags
- `addNotes` - Create multiple notes in bulk
  - Create many notes with specified parameters

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

## Installation

To use with Claude Desktop, add the server config:

On MacOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
On Windows: `%APPDATA%/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "anki-mcp": {
      "command": "node",
      "args": ["d:\\anki-mcp-server\\build\\index.js"]
    }
  }
}
```

### Installing via Smithery

To install Anki Integration Server for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@CamdenClark/anki-mcp-server):

```bash
npx -y @smithery/cli install @CamdenClark/anki-mcp-server --client claude
```

### Debugging

Since MCP servers communicate over stdio, debugging can be challenging. We recommend using the [MCP Inspector](https://github.com/modelcontextprotocol/inspector), which is available as a package script:

```bash
npm run inspector
```

The Inspector will provide a URL to access debugging tools in your browser.
