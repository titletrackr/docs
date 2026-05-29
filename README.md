# TitleTrackr Developer Docs

The source for the [TitleTrackr Developer API documentation](https://docs.titletrackr.com), built with [Mintlify](https://mintlify.com).

These docs cover the partner-facing API for pushing data into TitleTrackr — creating orders and uploading documents to the File Vault.

## Structure

```
docs.json              # Site config: navigation, theme, logos, links
custom.css             # Landing-page hero styling (dark green gradient)
openapi.json           # OpenAPI spec — powers the API Reference tab
introduction.mdx       # Custom "Build with TitleTrackr" landing page
authentication.mdx     # Bearer-token auth, errors, rate limits
requesting-access.mdx  # How to get an API key
orders/                # Orders API guides (overview, create, custom fields)
file-vault/            # File Vault API guides (overview, upload, folders, metadata)
logo/                  # light.png / dark.png navbar logos
```

The site has two tabs: **Guides** (the `.mdx` pages above) and **API Reference** (auto-generated from `openapi.json`).

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

Run the dev server from the repo root (where `docs.json` lives):

```bash
mint dev
```

View the local preview at `http://localhost:3000`.

Before pushing, validate the build and check links:

```bash
mint validate
mint broken-links
```

## Editing content

- Pages are MDX with YAML frontmatter (`title` is required; add `description` for SEO).
- Internal links use root-relative paths without extensions, e.g. `/orders/overview`.
- New pages must be added to the `navigation` in `docs.json` to appear in the sidebar.
- API endpoints come from `openapi.json` — update the spec to change the API Reference.
- The landing page (`introduction.mdx`) uses `mode: "custom"` and the styles in `custom.css`.

## Publishing

The repo is connected to Mintlify via its GitHub app. Pushing to `main` deploys to production automatically.

## Links

- [Live docs](https://docs.titletrackr.com)
- [TitleTrackr app](https://app.titletrackr.com)
- [Request API access](https://developer.titletrackr.com/request)
- [Mintlify documentation](https://mintlify.com/docs)
