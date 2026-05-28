# Template archive

Superseded template versions live here. The folder serves two purposes:

- **Reference** — historical schema for content authored against earlier versions.
- **Migration target** — a place migration scans can point at when the renderer drops support for an old version.

## Convention

- Bumping a template means moving the current latest into `_archive/` and authoring the new version at `templates/template-<entity>-v<X.Y.Z>.md`:

  ```bash
  git mv templates/template-essay-v1.0.0.md templates/_archive/
  # then author templates/template-essay-v1.1.0.md
  ```

- Filenames in `_archive/` keep their semver — that's how you know which version each archived template was.

- Archived templates are read-only by convention. If a fix is needed, bump the template (new version in `templates/`); don't edit history.

## Current contents

- `template-library-v1.md` — the category template covering book / paper / podcast / publisher / publication. Superseded by per-entity templates (`book`, `paper`, `publisher`, `publication`) at `templates/`.
- `template-report-v1.md` — the category template covering lightpaper / whitepaper / position-paper / model-paper. Superseded; the per-type split lands when content does.

See `docs/conventions/templates-and-versioning.md` for the full convention.
