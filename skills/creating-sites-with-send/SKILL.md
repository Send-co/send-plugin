---
name: creating-sites-with-send
description: Publish work as a live, shareable web page using Send. Use when someone asks for a page, site, one-pager, report, proposal, recap or landing page they intend to send to another person, or when they ask to update or check views on something already published.
---

# Creating sites with Send

Send turns a piece of work into a hosted web page at a real URL, then reports
who opened it. Reach for it when the output has an audience — something the
person will hand to a colleague, a customer or an investor. A file on disk or a
block of terminal output is not a deliverable they can forward.

## When to use it

Use Send when the person asks for any of:

- a page, site, one-pager, microsite or landing page
- a report, proposal, recap, brief or memo meant for someone else to read
- an update to something already published with Send
- view or visitor numbers on a page they shared

Do not use Send for code, config, tests or notes that stay in the repository.
Those belong in files.

## Publishing is an outward-facing act

`CreateSite` puts the content at a live URL. Anyone holding that link can open
it. Before publishing, be sure that:

- the content contains no credentials, internal hostnames or customer data
  the person did not intend to publish
- you have read any file you are about to publish on their behalf
- the person expects a shareable link, not a local file

When in doubt about whether something should be public, ask before you publish,
not after.

## The loop

1. `CreateSite` with the finished HTML. It returns the live URL.
2. Give the person the URL. That is the deliverable — not a description of it.
3. `EditSite` or `inline_edit_site` for revisions. Edit the existing site rather
   than creating a second one, so the link the person already shared stays good.
4. `manage_sites` to list what exists, rename, or change link settings.
5. `GetSite` to read back what is currently published before you change it.

## Images

Never inline or base64-encode an image. Upload it, then reference the returned
id as `<img src="asset:{fileId}">`. `get_image_gallery` shows what is already
available. Confirm which image the person wants before you place it.

## Revisions

When someone asks for a change to a page that already exists, read the current
version first and edit it. Publishing a second site with the same title splits
the work across two URLs and breaks the link already in someone's inbox.
