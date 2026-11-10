# Post Reddit comment

Automatically post Reddit comment on reddit.com. Post a top-level comment on a Reddit post by its URL. Returns the created comment's id, permalink, author, created timestamp and score. Posts a real comment under the logged-in account; this is a top-level comment on the post, not a reply to another comment. Runs only via the browser extension, not the hosted cloud browser.

- Site: reddit.com
- Address: `reduck/reddit.com/post_comment`
- Updated: 2026-10-22 (v14)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/reddit.com/post_comment`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/reddit.com/post_comment
```

## Input

- `url` (string, required): Post URL — full https://www.reddit.com/r/.../comments/... or just the /r/.../comments/... path
- `text` (string, required): Comment body (plain text / markdown). Supports inline @-mentions (u/name) and links, which Reddit auto-links.

## Output

- `author` (string, required)
- `commentId` (string, required): Fullname of the created comment, e.g. t1_xxxxx
- `permalink` (string, required)
- `account_used` (string, required): The real logged-in Reddit handle that performed the action, read from the page's own account drawer (not assumed from args)
- `already_present` (boolean, required): Whether an identical top-level comment by this account already existed on this post before posting (checked against the post's own comment list)
- `verified_on_page` (boolean, required): Whether the script reloaded the post afterward and confirmed the new comment is actually visible there
- `score` (number | null, optional)
- `created` (string | null, optional)

## FAQ

### What does "Post Reddit comment" do?

Post a top-level comment on a Reddit post by its URL. Returns the created comment's id, permalink, author, created timestamp and score. Posts a real comment under the logged-in account; this is a top-level comment on the post, not a reply to another comment. Runs only via the browser extension, not the hosted cloud browser.

### How do I automatically post Reddit comment on reddit.com?

Ask an AI agent connected to Reduck to run reduck/reddit.com/post_comment, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/post_comment

### Is there a reddit.com API to post Reddit comment?

You do not need one. "Post Reddit comment" drives the real reddit.com pages in a browser, so it works whether or not reddit.com offers an API for this.

### What information do I need to provide?

Required: url, text.

### What does it return?

It returns score, author, created, commentId, permalink, account_used, already_present, verified_on_page.

### Do I need to be logged in to reddit.com?

Yes. It acts as you on reddit.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the reddit.com cookies saved by the Reduck extension.

### Does it change anything on reddit.com, or only read data?

It makes changes on reddit.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/reddit.com/post_comment, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/post_comment

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/reddit.com/post_comment
