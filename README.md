# תורה צמחונית — דבר תורה צמחוני / טבעוני על פרשת השבוע

The site's source, migrated from Google Sites (`sites.google.com/view/vegantorah`) to GitHub Pages with Jekyll.

## Structure

| Path | Contents |
|---|---|
| `index.html` | Home page |
| `pages/*.html` | Every divrei torah page (weekly portions, holidays, Q&A and so on). Each file starts with a `title` and a `description`: the description is what Google shows in search results, so it's worth editing by hand |
| `_layouts/default.html` | The shared page template: SEO tags, schema.org data, breadcrumbs, previous/next links, share buttons |
| `assets/style.css` | Styling (right-to-left, mobile layout, dark mode) |

## Adding or editing a page
1. Create a file in `pages/` with front matter:
   ```
   ---
   title: "דבר תורה צמחוני / טבעוני על ..."
   description: "Up to about 155 characters summarizing the page"
   permalink: /page-address/
   type: article
   ---
   <h3>Heading</h3>
   <p>Text…</p>
   ```
2. Add a link to it on the home page (`index.html`).

## Turning on GitHub Pages
Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)`.
The site will be at `https://bambiker.github.io/vegantorah/`.

## Custom domain (recommended for SEO)
1. Buy a domain (for example `vegantorah.co.il`) and point its DNS records at GitHub Pages.
2. Settings → Pages → Custom domain.
3. In `_config.yml` change `url` to the domain and `baseurl` to `""`.

## Moving over from Google Sites
- Google Sites can't do 301 redirects. Once the new site is indexed, replace the content of each old page with a short "the site has moved" notice and a link to the matching new page, so that both sites don't stay up with duplicate content.
- Register the new site in Google Search Console, put the verification code in `_config.yml` (`webmaster_verifications`), and submit `sitemap.xml`.
- Update external links to the site (Facebook, other sites, email signatures).

## Running locally
```
bundle install
bundle exec jekyll serve
```
