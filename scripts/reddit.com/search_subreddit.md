# Search a Reddit subreddit

Automatically search a Reddit subreddit on reddit.com. Search posts within a single subreddit, with optional sort and time window, one page at a time. Returns subreddit, count, threads (each with id, url, title, author, score, num_comments, created, subreddit, nsfw, preview_text) and nextCursor: pass it as cursor, with the same subreddit, topic, sort and time, for the next page; it is null on the last page. A search with no matches returns count 0. Reddit ignores `time` when sort=new. When a query has no genuine matches, Reddit's own search sometimes returns a few loosely related posts from the subreddit instead of an empty result, with no way to tell them apart from real hits. Reddit's subreddit-scoped search cards show titles only, so preview_text is null here; for body excerpts use reddit.com/search_reddit with a `subreddit:name` term in the query.

- Site: reddit.com
- Address: `reduck/reddit.com/search_subreddit`
- Updated: 2026-10-22 (v13)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/reddit.com/search_subreddit`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_subreddit
```

## Input

- `topic` (string, required): Search query
- `subreddit` (string, required): Subreddit name, with or without the r/ prefix
- `sort` (string, optional): Reddit's native sort (default relevance)
- `time` (string, optional): Reddit's native time filter (default all). Ignored by Reddit when sort=new.
- `cursor` (string, optional): The nextCursor of the previous answer, to read the next page. Omit for the first page. Pass the same subreddit, topic, sort and time as for the first page.

## Output

- `count` (number, required)
- `threads` (array, required)
- `subreddit` (string, required)
- `nextCursor` (string | null, required): Pass as cursor to read the next page; null on the last page.

## FAQ

### What does "Search a Reddit subreddit" do?

Search posts within a single subreddit, with optional sort and time window, one page at a time. Returns subreddit, count, threads (each with id, url, title, author, score, num_comments, created, subreddit, nsfw, preview_text) and nextCursor: pass it as cursor, with the same subreddit, topic, sort and time, for the next page; it is null on the last page. A search with no matches returns count 0. Reddit ignores `time` when sort=new. When a query has no genuine matches, Reddit's own search sometimes returns a few loosely related posts from the subreddit instead of an empty result, with no way to tell them apart from real hits. Reddit's subreddit-scoped search cards show titles only, so preview_text is null here; for body excerpts use reddit.com/search_reddit with a `subreddit:name` term in the query.

### How do I automatically search a Reddit subreddit on reddit.com?

Ask an AI agent connected to Reduck to run reduck/reddit.com/search_subreddit, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_subreddit

### Is there a reddit.com API to search a Reddit subreddit?

You do not need one. "Search a Reddit subreddit" drives the real reddit.com pages in a browser, so it works whether or not reddit.com offers an API for this.

### What information do I need to provide?

Required: subreddit, topic. Optional: sort, time, cursor.

### What does it return?

It returns count, threads, subreddit, nextCursor.

### Do I need to be logged in to reddit.com?

No. It only uses pages of reddit.com that are reachable without signing in.

### Does it change anything on reddit.com, or only read data?

It only reads. It looks things up on reddit.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/reddit.com/search_subreddit, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/search_subreddit

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/reddit.com/search_subreddit
