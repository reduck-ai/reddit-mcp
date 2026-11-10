# Reply to Reddit comment

Automatically reply to Reddit comment on reddit.com. Reply to a Reddit comment at any nesting depth, by its permalink. Returns the new reply's id, permalink, author and depth. Posts a real, public reply under the logged-in account. Runs only via the browser extension, not the hosted cloud browser.

- Site: reddit.com
- Address: `reduck/reddit.com/reply_comment`
- Updated: 2026-10-22 (v8)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/reddit.com/reply_comment`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/reddit.com/reply_comment
```

## Input

- `text` (string, required): Reply body (plain text / markdown). Supports inline @-mentions (u/name) and links, which Reddit auto-links.
- `permalink` (string, required): The target comment's permalink (relative path or full URL), e.g. /r/test/comments/<postid>/comment/<commentid>/ — as returned by post_comment or get_post

## Output

- `parentId` (string, required): Fullname of the comment replied to
- `commentId` (string, required): Fullname of the created reply, e.g. t1_xxxxx
- `permalink` (string, required)
- `account_used` (string, required): The real logged-in Reddit handle that performed the action, read from the page's own account drawer (not assumed from args)
- `already_present` (boolean, required): Whether an identical reply by this account already existed directly under the target comment before replying
- `verified_on_page` (boolean, required): Whether the script reloaded the page afterward and confirmed the new reply is actually visible under the target comment
- `depth` (number | null, optional): Nesting depth of the created reply (0 = top-level)
- `author` (string | null, optional)

## FAQ

### What does "Reply to Reddit comment" do?

Reply to a Reddit comment at any nesting depth, by its permalink. Returns the new reply's id, permalink, author and depth. Posts a real, public reply under the logged-in account. Runs only via the browser extension, not the hosted cloud browser.

### How do I automatically reply to Reddit comment on reddit.com?

Ask an AI agent connected to Reduck to run reduck/reddit.com/reply_comment, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/reply_comment

### Is there a reddit.com API to reply to Reddit comment?

You do not need one. "Reply to Reddit comment" drives the real reddit.com pages in a browser, so it works whether or not reddit.com offers an API for this.

### What information do I need to provide?

Required: permalink, text.

### What does it return?

It returns depth, author, parentId, commentId, permalink, account_used, already_present, verified_on_page.

### Do I need to be logged in to reddit.com?

Yes. It acts as you on reddit.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the reddit.com cookies saved by the Reduck extension.

### Does it change anything on reddit.com, or only read data?

It makes changes on reddit.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/reddit.com/reply_comment, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/reddit.com/reply_comment

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/reddit.com/reply_comment
