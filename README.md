# MLE Interview Prep

A [Quarto](https://quarto.org) website of from-scratch implementations and notes
for machine-learning engineer interviews: math foundations, classical ML, deep
learning, modern architectures, and production topics.

## Develop

```bash
# install deps (uses uv + the project .venv)
uv sync

# live preview with hot reload
quarto preview

# build the static site into docs/
quarto render
```

Notebooks are rendered from their stored outputs (`execute.enabled: false` in
[`_quarto.yml`](_quarto.yml)), so a full build doesn't re-run the heavy
torch/distributed code. Run a notebook in Jupyter/VS Code to refresh its
outputs, then re-render.

## Publish

Pushing to `main` triggers [`.github/workflows/publish.yml`](.github/workflows/publish.yml),
which renders the site on GitHub's servers and deploys it to GitHub Pages.
The built `docs/` is not committed (it's git-ignored).

One-time setup: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
The site is then served at `https://<user>.github.io/mle-interview/`.
