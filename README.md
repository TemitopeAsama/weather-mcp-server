# Weather MCP Server

A lightweight TypeScript [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server that retrieves active weather alerts for US states from the National Weather Service API.

## Tool

### `get-alerts`

Input:

- `state` — two-letter US state code, such as `CA` or `NY` (case-insensitive).

Returns the headlines of active alerts for that state, or a message when there are no active alerts. API errors are returned as tool errors.

## Requirements

- Node.js
- An MCP-compatible client

## Run

Install dependencies and start the server over standard input/output:

```sh
npm install
npx tsx src/index.ts
```

The process communicates with its MCP client over stdio. Configure your MCP client to launch `npx` with arguments `tsx` and `src/index.ts`, using this project directory as its working directory.

## Data source

Weather alerts are requested from the [National Weather Service API](https://api.weather.gov/alerts/active). The service currently covers the United States.

## License

ISC (see `package.json`).
