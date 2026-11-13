# Get Reddit subreddit threads

Automatically get Reddit subreddit threads on reddit.com. List a subreddit's threads by Reddit's native sort (best/hot/new/top/rising). "new" is chronological (filter with `since`); "top" takes a `time` window (hour…all); others paginate by `limit`. Returns url, title, author, score, num_comments, created, post_type, and body — the post's full text (never truncated; null for link/image posts). `limit` is a maximum, not a guarantee: fewer matching threads returns what exists.

- Site: reddit.com
- Address: `reduck/reddit.com/get_subreddit_threads`
- Updated: 2026-11-12 (v33)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/reddit.com/get_subreddit_threads`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/reddit.com/get_subreddit_threads
```

## Input

- `sort` (string, optional): Reddit's native subreddit sort. "new" is chronological (supports `since`); best/hot/top/rising are ranked (use `limit`). Default new.
- `time` (string, optional): Time window for sort:"top" only (default all). Rejected for other sorts.
- `limit` (number, optional): Max number of threads to return (newest first). With `since` and no `limit`, the time window is the only bound: every post in it is returned. With neither, 25. A maximum, not a guarantee: fewer matching threads returns what exists.
- `since` (string, optional): sort:"new" only - how far back to go: ISO date ("2026-06-01") or shorthand ("24h", "7d", "2w"). Combine with `limit` to cap a time window.
- `subreddit` (string, optional): Subreddit name, with or without the r/ prefix. Case-insensitive: Reddit redirects to the canonical casing (r/python -> r/Python) and the script follows it.
- `subreddits` (array, optional): Not supported since 19 Oct 2026: the run fails with a message saying so. Send one subreddit per call and fan out with run_script's scripts.

## Output

- `count` (number, optional)
- `threads` (any, optional)
- `complete` (boolean, optional): true when the feed (or the `since` window) ended before `limit` was reached, so every thread it holds is here; false when `limit` stopped the read and more threads exist.
- `subreddit` (string, optional)

## FAQ

### What does "Get Reddit subreddit threads" do?

List a subreddit's threads by Reddit's native sort (best/hot/new/top/rising). "new" is chronological (filter with `since`); "top" takes a `time` window (hour…all); others paginate by `limit`. Returns url, title, author, score, num_comments, created, post_type, and body — the post's full text (never truncated; null for link/image posts). `limit` is a maximum, not a guarantee: fewer matching threads returns what exists.

### How do I automatically get Reddit subreddit threads on reddit.com?

Ask an AI agent connected to Reduck to run reduck/reddit.com/get_subreddit_threads, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/get_subreddit_threads

### Is there a reddit.com API to get Reddit subreddit threads?

You do not need one. "Get Reddit subreddit threads" drives the real reddit.com pages in a browser, so it works whether or not reddit.com offers an API for this.

### What information do I need to provide?

Optional: sort, time, limit, since, subreddit, subreddits.

### What does it return?

It returns count, threads, complete, subreddit.

### Do I need to be logged in to reddit.com?

No. It only uses pages of reddit.com that are reachable without signing in.

### Does it change anything on reddit.com, or only read data?

It only reads. It looks things up on reddit.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/reddit.com/get_subreddit_threads, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/get_subreddit_threads

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/reddit.com/get_subreddit_threads
