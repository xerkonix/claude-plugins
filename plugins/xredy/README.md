# XREDY for Claude

XREDY keeps your company's knowledge pages, datasets and entity types in one place. This plugin connects Claude Code to your XREDY space so Claude can search and read what your team has approved and published, and suggest changes that a person reviews in XREDY.

## Install

```
/plugin marketplace add xerkonix/claude-plugins
/plugin install xredy@xerkonix
```

The first time Claude uses XREDY, your browser opens the XREDY sign-in and consent page. Choose the space and the access you allow, then return to Claude Code. To change that access later, reconnect from `/mcp`.

Connection guide: https://xredy.com/docs/mcp

## What it includes

- **MCP server**: the XREDY remote MCP server at `https://xredy.com/mcp`, over HTTPS with OAuth 2.0. The plugin sends nothing anywhere else and runs no local code.
- **Skill** `xredy`: tells Claude which XREDY tool fits a question and how a suggestion is reviewed.

## Tools

| Tool | What it does | Access |
|---|---|---|
| `xredy_search` | Search pages, datasets and entity types together | Read |
| `xredy_fetch` | Read one search result by its typed id | Read |
| `xredy_search_pages` | Search knowledge pages | Read |
| `xredy_list_pages` | List knowledge pages, optionally by topic | Read |
| `xredy_get_page` | Read one page with its sentence numbers and sources | Read |
| `xredy_list_datasets` | List published datasets | Read |
| `xredy_get_dataset` | Read a dataset's columns and first rows | Read |
| `xredy_query_dataset` | Filter a dataset's rows | Read |
| `xredy_list_types` | List approved entity types | Read |
| `xredy_get_type` | Read one entity type | Read |
| `xredy_propose_knowledge` | Suggest a sentence or a new page; an owner or admin approves it in XREDY | Write |

Dataset tools appear when you allow dataset access, and `xredy_propose_knowledge` when you allow suggestions.

## Privacy

XERKONIX processes the data you send through this connection under the [XERKONIX privacy policy](https://xerkonix.com/privacy). Terms: https://xerkonix.com/terms

## Support

contact@xerkonix.com

## License

[MIT](LICENSE)
