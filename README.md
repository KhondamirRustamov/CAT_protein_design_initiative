# CAT Protein Design Initiative — website

Static, self-contained site. `index.html` has all assets (structure file, figures, viewer, photos) inlined — no build step, no dependencies.

## Publish on GitHub Pages

```bash
cd deploy
git init -b main
git add .
git commit -m "CAT Protein Design Initiative website"
gh repo create CAT_protein_design_initiative --public --source=. --push
gh api -X POST repos/:owner/CAT_protein_design_initiative/pages \
  -f source[branch]=main -f source[path]=/
```

Without the `gh` CLI: create a public repo named `CAT_protein_design_initiative` on github.com, push this folder to `main`, then Settings → Pages → Source: `main` / root.

Live URL: `https://<your-username>.github.io/CAT_protein_design_initiative/`

## Custom domain

Add a `CNAME` file containing the domain, point a DNS CNAME at `<your-username>.github.io`, then enable it under Settings → Pages.

## Updating

Re-export `index.html` and commit over it. Pages redeploys within a minute.
