# Reddit MCP

A Reddit MCP server that works as you: search Reddit, read full threads with every comment, read a subreddit, and post or reply, from Claude, ChatGPT or Cursor. No API key, no OAuth app, no RSS feed.

- Product: Reduck MCP
- Updated: 2026-10-05

![One integration, every website](https://docs.reduck.ai/overview/one-integration-every-website.png)

[Reduck MCP](https://docs.reduck.ai) gives your agent reusable browser scripts for the sites that have no API. They run in your own Chrome, through the Reduck extension, where you are already signed in: no credentials exposed, and no bot detection.

**Get started:** [docs.reduck.ai](https://docs.reduck.ai)

## Overview

Reddit is where people say what they really think about a product, a tool or a problem. An AI agent can read your email, your docs and your CRM, but when you ask it what a thread on Reddit said, it gets a refusal or an empty page.

## Why it's hard

An agent has three ways into Reddit, and each one is closing. The public Data API needs an approved app, no longer accepts new requests after October 31, 2026, and closes in March 2027. RSS feeds stop on November 13, 2026. Unauthenticated `.json` requests answer 403, and Reddit refuses connections from datacenter addresses, where cloud browsers and most agents run. On top of that, Claude's own web fetch declines reddit.com, and Claude in Chrome has refused every Reddit page since September 18, 2026.

## How Reduck does it

Reduck is an MCP server whose Reddit scripts run in your own Chrome, where you are already signed in to Reddit. Your agent reads what you see: search results across Reddit or inside one subreddit, a subreddit's threads, and full threads with every comment. It comments and replies only when you ask. There is no API key, no OAuth app, no RSS feed and no separate account.

## Tools

| Script | What it does | Takes |
|---|---|---|
| `search_reddit` | Posts across all of Reddit for a query, with a time window | a query, how many |
| `search_subreddit` | Posts inside one subreddit, newest first or by score | a subreddit, a query |
| `get_subreddit_threads` | A subreddit's threads by hot, new, top or rising, with each post's full text | a subreddit, a sort |
| `get_thread` | A full thread: the post, its score and every comment with its depth | its url |
| `get_user` | A user's profile, karma and recent posts and comments | a username |
| `post_comment` | A top-level comment on a post | its url, the text |
| `reply_comment` | A reply to a comment at any depth | its url, the text |

Every script answers structured data: ids, links, authors, dates, scores and the text as Reddit shows it. The summary and the reasoning stay in your agent. The full list of Reddit scripts is in the [catalogue](https://reduck.ai/explore?host=reddit.com).

## Connect it

1. Install the Reduck extension in Chrome and stay signed in to Reddit there.
2. Add Reduck to your client: [Claude Code](https://docs.reduck.ai/claude-code), [Claude Desktop](https://docs.reduck.ai/claude-desktop), [ChatGPT](https://docs.reduck.ai/chatgpt) or [any other MCP client](https://docs.reduck.ai/other-clients).
3. Ask: "Read the top threads of the week in r/webscraping about Reddit's API shutdown and tell me what people plan to do instead."

## Reddit API or Reduck

| | Reddit API and API-based MCPs | Reduck |
|---|---|---|
| Setup | A registered, approved app and OAuth credentials | Stay signed in to Reddit in Chrome |
| After March 2027 | Only through the Developer Platform or a licence | Unchanged: it reads the pages you read |
| Acts as | Your app | You, in your browser |
| Full threads | Through the API, within its rate limits | Yes, every comment as you see it |
| Posting | Through the API, as your app | Yes, as you |

What Reddit announced, with the dates: [What Reddit September 2026 API and RSS shutdown implies and how to keep using Reddit with your agent](https://blog.reduck.ai/reddit-api-rss-shutdown-ai-agents/).

## Who it's for

- Founders and marketers who follow what people say about their product on Reddit
- Researchers who read a few subreddits every week from an AI agent
- Developers whose Reddit integration breaks with the end of RSS and the public API

## FAQ

### Why can't Claude read Reddit on its own?

Claude's web fetch declines reddit.com, and since September 18, 2026 Claude in Chrome refuses every Reddit page with "not allowed due to safety restrictions" (anthropics/claude-code issue #95326). Reduck does not go through either: its Reddit scripts run in your own Chrome, through the Reduck extension, where you are signed in to Reddit.

### Do I need a Reddit API key or an OAuth app?

No. There is no app to register and no key to paste. You stay signed in to Reddit in your own Chrome, and the Reduck extension runs each script there.

### Does it still work after Reddit ends RSS and its public API?

Yes. Reddit stops RSS feeds on November 13, 2026 and closes its public Data API in March 2027. Reduck reads the pages you can read while signed in, so it does not depend on either.

### Can it read a full thread, with every comment?

Yes. get_thread returns the post, its score and its comments with their depth, so the agent can rebuild the tree. With all_comments it opens every "more replies" link too.

### Can it post and reply for me?

Yes, and only when asked. post_comment posts a top-level comment and reply_comment answers a comment at any depth, under your account. The agent shows you the exact text first, and each script returns the new comment's link.

### Is there an official Reddit MCP server?

Not documented. Reddit points developers to its Developer Platform (Devvit), which runs apps inside Reddit, not an outside agent reading posts. The community Reddit MCP servers on GitHub mostly call the Reddit API with your own app credentials.

### Is this allowed by Reddit's rules?

Reddit's rules forbid unauthorized scraping and bulk collection, whatever tool does it. Reduck reads at your pace, in your own session: what you could open and read yourself. For bulk data, or Reddit data inside a product you sell, ask Reddit for data access.

### Does it work with ChatGPT, Claude and Cursor?

Yes. Reduck connects to ChatGPT, Claude, Claude Code, Codex, Cursor and any other MCP client. You ask in plain words, and the agent picks the Reddit scripts it needs.

Source: https://reduck.ai/use-cases/reddit-mcp
