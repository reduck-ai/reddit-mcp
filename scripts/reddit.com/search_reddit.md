# Search Reddit

Automatically search Reddit on reddit.com. Search posts across all of Reddit, with Reddit's own sort and time window. Returns count and threads (id, url, title, author, subreddit, score, num_comments, created, nsfw, preview_text) in the order Reddit lists them. `limit` is a maximum: fewer matching posts return what exists, and no match returns count 0. Reddit matches loosely, so under the `top` sort a heavily upvoted post only loosely related to the query can come before closer matches; use the default `relevance` sort when on-topic results matter.

- Site: reddit.com
- Address: `reduck/reddit.com/search_reddit`
- Updated: 2026-10-29 (v23)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/reddit.com/search_reddit`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_reddit
```

## Input

- `sort` (string, optional): Reddit's native sort (default relevance)
- `time` (string, optional): Reddit's native time filter (default all). Ignored by Reddit when sort=new.
- `limit` (number, optional): Max results, paginating via the site's own infinite scroll (default 25)
- `query` (string, optional): Alias for `topic` (accepted for compatibility — prefer `topic`).
- `topic` (string, optional): Search query. Canonical name for this field; `query` is accepted as an alias.
- `queries` (array, optional): Not supported since 19 Oct 2026: the run fails with a message saying so. Send one topic per call and fan out with run_script's scripts.

## Output

- `count` (number, required)
- `threads` (any, required)

## FAQ

### What does "Search Reddit" do?

Search posts across all of Reddit, with Reddit's own sort and time window. Returns count and threads (id, url, title, author, subreddit, score, num_comments, created, nsfw, preview_text) in the order Reddit lists them. `limit` is a maximum: fewer matching posts return what exists, and no match returns count 0. Reddit matches loosely, so under the `top` sort a heavily upvoted post only loosely related to the query can come before closer matches; use the default `relevance` sort when on-topic results matter.

### How do I automatically search Reddit on reddit.com?

Ask an AI agent connected to Reduck to run reduck/reddit.com/search_reddit, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_reddit

### Is there a reddit.com API to search Reddit?

You do not need one. "Search Reddit" drives the real reddit.com pages in a browser, so it works whether or not reddit.com offers an API for this.

### What information do I need to provide?

Optional: sort, time, limit, query, topic, queries.

### What does it return?

It returns count, threads.

### Do I need to be logged in to reddit.com?

No. It only uses pages of reddit.com that are reachable without signing in.

### Does it change anything on reddit.com, or only read data?

It only reads. It looks things up on reddit.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/reddit.com/search_reddit, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_reddit

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/reddit.com/search_reddit
