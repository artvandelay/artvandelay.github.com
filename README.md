# artvandelay.github.com

Source for <https://artvandelay.github.io/>.

Plain static `index.html` listing all my public, non-archived GitHub Pages
sites. The list is regenerated nightly by `.github/workflows/update.yml`
which runs `scripts/generate.sh`.

## How it works

1. `scripts/generate.sh` calls the GitHub API for repos owned by `artvandelay`
   that have Pages enabled and aren't archived or forks.
2. It rewrites the `<!-- PROJECTS:START --> ... <!-- PROJECTS:END -->` block
   inside `index.html`.
3. The workflow commits any change back to `master`.

`.nojekyll` disables GitHub Pages' Jekyll processing — this is a plain static
site, served as-is.

## Local regenerate

```bash
gh auth login   # if needed
./scripts/generate.sh
```
