# How to use these files

These are meant to be dropped into your existing `corvids-cairn-studio.github.io`
repo, not used as a brand new site — your repo already has Jekyll + GitHub Pages
working, this just replaces the homepage/post look.

## 1. Copy files in

Copy these into your repo, preserving the folder structure:

- `_config.yml` → **don't overwrite your existing one.** Open both side by
  side and copy in whichever keys you don't already have (paginate,
  paginate_path, plugins, defaults, permalink). Keep your current title/url
  if they're already set correctly.
- `_layouts/default.html`, `_layouts/home.html`, `_layouts/post.html` → copy
  in as-is. If you already have layouts with these names from the `slate`
  theme, these will replace them.
- `assets/css/style.css` → copy in as-is (new file).
- `index.md` → replace your current homepage file with this one (or copy
  the front matter `layout: home` into whatever file currently serves as
  your homepage).
- `_posts/*.md` → these two are **example posts** showing the front matter
  format. Delete them once you've written real ones, or keep them as a
  reference for the format.

## 2. Write a real devlog post

Every post is a Markdown file in `_posts/`, named:

```
YYYY-MM-DD-a-url-safe-title.md
```

With this front matter at the top:

```yaml
---
title: "Your post title here"
categories: [SpaceSects, process]
---
```

Use whatever categories fit — `SpaceSects` / `Project Last Light` / `studio`
for the project, and `process` / `lore` / `updates` for the kind of post.
Both show up automatically in the post list and on the post page — no
template editing needed per post.

Everything after the `---` is normal Markdown: headings, images, links,
code blocks all work.

## 3. Commit and push

GitHub Pages rebuilds automatically on push — no build step to run
yourself. Give it a minute or two after pushing, then check the live site.

## 4. What's still yours to decide

- The nav links in `_layouts/default.html` point to placeholder URLs
  (`github.com/corvids-cairn-studio`, `youtube.com/@ShortyTheCrow`,
  `shortanel.itch.io`, and a `mailto:` contact) — double check these match
  your actual final links.
- The small pixel logo in the header is the simplified inline SVG from
  earlier — swap it for your finished pixel-art logo file once it exists,
  as an `<img>` tag instead of inline SVG.
- Pagination shows 5 posts per page (1 featured + 4 listed) by default —
  change the `paginate:` number in `_config.yml` to adjust.
- The featured "latest entry" block always shows the first post on
  whichever page you're viewing — meaning on page 2 it'll highlight the
  oldest post *within* that page, not just page 1. Fine for now, but worth
  knowing if it looks odd once you have many posts.
