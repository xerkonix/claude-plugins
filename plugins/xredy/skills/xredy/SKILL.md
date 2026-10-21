---
name: xredy
description: Use when the user asks about their company's own knowledge, records or terms kept in XREDY — approved knowledge pages, published datasets, or entity types — or wants to suggest a change to a knowledge page.
---

# Working with XREDY

XREDY keeps a company's knowledge in three forms. The connected account sees only its own space.

- **Pages**: approved knowledge pages. Each sentence carries a number (`s1`, `s2`, …) and source references.
- **Datasets**: published tables with columns and rows. Drafts are not visible.
- **Entity types**: approved company terms with synonyms and attribute candidates.

## Find, then read

1. Start with `xredy_search` when you don't know where the answer lives. It searches pages, datasets and entity types together and returns typed ids such as `page:…`, `dataset:…` and `type:…`.
2. Read a result with `xredy_fetch` and its typed id.
3. Use the narrower tools when the user names the kind:
   - Pages: `xredy_search_pages`, `xredy_list_pages`, `xredy_get_page`
   - Datasets: `xredy_list_datasets`, `xredy_get_dataset` (columns and the first rows), `xredy_query_dataset` (filtered rows, with `nextCursor` for the next batch)
   - Entity types: `xredy_list_types`, `xredy_get_type`

When you answer from XREDY, name the page, dataset or entity type you used and include its link when the result has one.

## Suggest a change

`xredy_propose_knowledge` sends a suggestion for a page. It doesn't change the page: an owner or admin reviews it in XREDY and approves or declines it. The tool is available only when the user allowed suggestions while connecting.

- `add`: a new sentence for an existing page, optionally under a heading, or a new page with a `title`.
- `modify`: replace one sentence. Read the page with `xredy_get_page` first and pass the sentence number as `target` and the page `version` you read.

Tell the user that the suggestion is waiting for review in XREDY.

## When a tool isn't listed

Dataset tools appear only when the user allowed dataset access while connecting, and the suggestion tool only when they allowed suggestions. If a tool the user needs is missing, tell them to reconnect XREDY and allow that access.
