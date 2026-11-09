# PerilOrder case studies

Two self-contained static pages with a toggle between them. No build step,
no dependencies, no external requests.

    index.html      NCIUA roof grant allocation (residual insurer)   -> /
    johnson.html    Johnson, Vermont wastewater plant (local gov)    -> /johnson

## Deploy

Replace the contents of the existing Vercel project with this folder, then

    npx vercel --prod

or drag the folder onto vercel.com/new.

## Notes

- `vercel.json` sets `cleanUrls`, so `johnson.html` is served at `/johnson`.
- `X-Robots-Tag: noindex, nofollow` is set on every response, `robots.txt`
  disallows all crawlers, and each page carries a `noindex` meta tag.
  A Vercel URL is public to anyone holding the link; this only keeps it out
  of search results.
- To make Johnson the landing page instead, swap the two filenames and flip
  the `on` class and `href` values in the `<nav class="switch">` block at the
  top of each page.
- The "Request an analysis" buttons are `mailto:` links. Change the address
  in both files if that should not be a personal inbox.
