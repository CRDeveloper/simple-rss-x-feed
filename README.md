# simple-rss-x-feed

A minimal public RSS feed hosted as a raw file on GitHub.  
Use it to auto-post short updates to X (Twitter) via IFTTT (or any tool that can read an RSS feed).

This is a lightweight workaround for people who want scheduled or automated posts without managing X API keys themselves or risking browser automation.

## How it works

1. This repo contains a single `rss.xml` file.
2. You (or a bot/script) update `rss.xml` by adding new `<item>` entries.
3. IFTTT (free tier is fine for low volume) watches the raw URL of `rss.xml` and posts new items to your X account.

The raw URL looks like:  
`https://raw.githubusercontent.com/YOUR_USERNAME/simple-rss-x-feed/main/rss.xml`

## Quick setup

1. **Fork this repo** (or create your own with the same structure).
2. Edit `rss.xml` — replace the example items with your own content.
3. In IFTTT:
   - Create a new Applet.
   - Trigger: **RSS Feed** → **New feed item**
   - Paste your raw `rss.xml` URL.
   - Action: **X (Twitter)** → **Post a tweet**
   - Customize the tweet text using the feed title/description.
4. Turn the Applet on.

Free IFTTT accounts can handle a few posts per day easily.

## Updating the feed

You can edit `rss.xml` directly on GitHub, use the GitHub API, a script, or a bot.  
Each new post should be a new `<item>` near the top of the channel.

Keep posts under 280 characters if you want them to fit cleanly in a single X post.

## Notes

- The repo is public so the raw URL is readable by IFTTT. Write access is still limited to people who have permission on the repo.
- This is intentionally simple. No fancy generator, no database. Just a file.
- Feel free to adapt it for other platforms that accept RSS.

---

Made as a simple shared starting point. Fork it, change the content, and make it yours.
