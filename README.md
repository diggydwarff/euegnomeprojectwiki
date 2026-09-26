# Nations Registry

A lightweight MkDocs site for server nations, governments, geography, culture, and laws.

Every nation uses the same main navigation — **Overview, Government, Geography, Culture, Laws** — but each nation may organize its **Laws** section however its own government actually works. Ardennes includes a developed code structure; Flux intentionally does not assume one yet.

## Publish on GitHub Pages

1. Create a new GitHub repository, for example `nations-registry`.
2. Extract this ZIP and upload **the contents of the `nations-registry` folder** to the repository's `main` branch.
3. Open `mkdocs.yml` and replace `YOURUSERNAME` in `site_url` with your GitHub username.
4. In GitHub, open **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to **GitHub Actions**.
6. Push any change, or open **Actions** and run `Deploy MkDocs to GitHub Pages` manually.
7. After the workflow finishes, the site should be available at:

   `https://YOURUSERNAME.github.io/nations-registry/`

## Editing Content

All public content lives under `docs/` as Markdown files.

```text
docs/
├── ardennes/
│   ├── index.md
│   ├── government.md
│   ├── geography.md
│   ├── culture.md
│   └── laws/
└── flux/
    ├── index.md
    ├── government.md
    ├── geography.md
    ├── culture.md
    └── laws/
```

### Adding a Nation

1. Copy one of the nation folders.
2. Rename it.
3. Replace the Markdown content.
4. Add the nation to the `nav:` section of `mkdocs.yml`.

### Giving a Nation Its Own Legal Structure

Do not copy Ardennes' legal categories unless that nation actually uses them. Create whatever files make sense for that nation's system, then list them beneath that nation's **Laws** entry in `mkdocs.yml`.

Example only:

```yaml
- Example Nation:
    - Overview: example/index.md
    - Government: example/government.md
    - Geography: example/geography.md
    - Culture: example/culture.md
    - Laws:
        - Legal System: example/laws/index.md
        - Decrees: example/laws/decrees.md
        - Council Orders: example/laws/council-orders.md
```

## Local Preview (Optional)

```bash
python -m pip install -r requirements.txt
mkdocs serve
```

Then open the local address printed by MkDocs.

## Custom Domain (Optional)

GitHub Pages can use a custom domain later. Configure it in **Settings → Pages → Custom domain** and follow GitHub's DNS instructions for your domain provider.
