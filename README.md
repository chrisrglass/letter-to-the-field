# Letter to the Field

Static archive of [lettertothefield.com](https://lettertothefield.com), a WordPress/Elementor site by Chris R. Glass. Mirrored 2026-09-12 with `wget --mirror`; 25 posts, the home page, and the full media library.

Served with GitHub Pages at https://chrisrglass.github.io/letter-to-the-field/

## Layout

- `index.html` and one folder per post (`<slug>/index.html`): the rendered pages.
- `wp-content/uploads/`: images (all sizes), self-hosted Google Fonts, and the combined CSS.
- `wp-includes/`, `wp-content/plugins/`, `wp-content/themes/`: scripts and styles the pages reference.
- `archive/wp-api/`: JSON snapshots of the public WordPress REST API (posts, pages, media, categories, tags) as a content backup. Add `archive/lettertothefield.WordPress.<date>.xml` (Tools → Export) for the full WXR backup.

## Serving from a custom domain later

Absolute links were rewritten to the `/letter-to-the-field/` base path so the site works under the project URL. To serve from a domain root instead (for example, pointing `lettertothefield.com` at GitHub Pages), replace that prefix with `/` in all text files and add a `CNAME` file:

```
grep -rl '/letter-to-the-field/' --include='*.html' --include='*.css' --include='*.js' . | xargs sed -i '' 's#/letter-to-the-field/#/#g'
echo lettertothefield.com > CNAME
```

`.nojekyll` tells GitHub Pages to publish the files as-is.
