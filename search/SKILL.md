---
name: search
description: This skill helps you with searching the web using `pi` command.
---

# search

Use CLI commands to search web with `pi` command.

DO NOT run these command directly in current context.

## When to use

Use for search, research.

## Instructions

In order to keep the context window small, never use these curls in current context.

Always use `pi` command to search. Example:

```bash
timeout 60 pi -p "use search skill to {{SPECIFY YOUR QUERY}}"
```

### Exa Search

Here is an example on how to use exa APIs.

```bash
curl -X POST "https://api.exa.ai/search" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $EXA_API_KEY" \
  -d '{"query": "YOUR QUERY"}'
```

DO NOT read $EXA_API_KEY from your environment variables.
If it's not available or limit reached fallback to Serp API search.

### Serp API

```bash
curl --get https://serpapi.com/search \
 -d engine="google" \
 -d q="YOUR QUERY" \
 -d kl="us-en"
```

If Serp API is not available fallback to Firecrawl Search.

### Firecrawl Search

```bash
firecrawl search "YOUR QUERY"
```

If Firecrawl doesn't work fallback to DuckDuckGo HTML Search.

### DuckDuckGo HTML Search

```bash
curl --get https://html.duckduckgo.com/html/?q=YOUR+QUERY
```

Note: this returns html, so you need to parse it.
