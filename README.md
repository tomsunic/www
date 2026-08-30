# Tom Sunic

Tom Sunic's website source repository.


To run on macbook locally:

```bash
#!/bin/bash
# Activate virtual environment
source venv/bin/activate
# Upgrade pip
pip install --upgrade pip
# Install MkDocs and necessary plugins
pip install mkdocs mkdocs-material mkdocs-meta-descriptions-plugin "mkdocs-material[imaging]"
# Verify installation (optional)
pip list | grep mkdocs
# Start MkDocs server
mkdocs serve
```

First time, create the virtual environment before activating it:

```bash
python3 -m venv venv
```

The site then runs on <http://127.0.0.1:8000>.

On macOS the `social` plugin needs the Cairo library, which pip cannot install.
Without it every page logs a `cairosvg` warning and the social preview cards are
skipped; the site itself still builds and serves. To silence it:

```bash
brew install cairo
```

GitHub Actions builds with `--strict`, and its Ubuntu runner already has Cairo,
so this is a local-only difference.

## Structure

- `docs/index.md` is the blog index. Posts live in `docs/posts/`, one file each,
  with `<!-- more -->` marking where the excerpt on the index stops.
- `docs/books.md` is the books page, one `<div class="book">` block per title.
- `docs/biblioteka/` holds full books published on the site, one folder per book.
- `docs/stylesheets/extra.css` holds the theme changes on top of
  mkdocs-material. It is built on Material's CSS variables, so light and dark
  both keep working.
- `mkdocs.yml` `nav` decides what appears in the top tabs and the sidebar. A page
  that is not in `nav` is built but linked from nowhere.
