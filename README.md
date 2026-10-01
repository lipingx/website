# Personal website

Live site: https://lipingx.github.io/website/

Written in Obsidian, rendered with Jekyll, and hosted on GitHub Pages.

## Publish a post

1. Edit the original note in the private vault and mark it `publish: true`.
2. Run the publishing exporter to copy the selected note and referenced images into this vault.
3. Review the changes, commit them, and push to `main`.
4. The **Build and deploy Jekyll site** GitHub Actions workflow builds and publishes the site.

`Posts/*.md` files are rendered as pages with a shared post layout and listed on the homepage. No dated filenames are required. A `title` property is optional (the filename is the fallback); `created` supplies the displayed date. Post URLs retain the `Posts/name.html` structure so the exporter's `../assets/images/` links resolve correctly. Avoid overriding a post's permalink without adjusting image links.

`Projects/*.md` files with YAML frontmatter are listed on the Projects page. Add those public files explicitly; the current exporter is for posts.

All files committed to this public repository are public, regardless of any publishing flag. The flag is checked by the private-vault exporter; it is not a privacy control here. Remove an exported copy and push to remove its page; Git history retains prior commits.

## Site files

- `_config.yml`: site name, URL, project base path, and layout defaults.
- `_layouts/`: shared page and article templates.
- `assets/css/style.css`: responsive styling.
- `.github/workflows/pages.yml`: build and deployment.

Obsidian settings and generated `_site/` files are ignored. Jekyll runs on GitHub, so local Ruby installation is not required to publish. After purchasing a custom domain, configure it in GitHub Pages settings and update `url` and `baseurl` here.

## Bilingual articles

Keep language versions in separate Markdown files with `lang: zh-CN` or `lang: en`, a language-specific `title`, and the same `translation_key` (for example `hillbilly-elegy`). Both versions retain their own publishing flag. The homepage groups them into one entry; each article links to its available translation. An unpaired post still appears normally. The previous Chinese article URL redirects to its new page.
