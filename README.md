# nanoco-learning-artifacts

Shared HTML development environment for NanoCo learning materials.

## Workflow

1. Elia works with **ChatGPT** on methodology and copy.
2. ChatGPT generates HTML/CSS structure.
3. **Claude** (NanoClaw agent) saves files to this repo, commits, and pushes.
4. **Vercel** auto-deploys on every push:
   - `main` → production
   - any branch → preview URL
5. Claude returns the preview URL to Elia.

## Structure

```
/projects
  /agent-readiness-framework   ← main NanoCo Discovery + Agent Design methodology
  /faye-playbook
  /nanoclaw-onboarding
/shared
  /css                          ← nanoco-design-system.css (brand tokens, components)
  /assets                       ← images, logos, icons
  /components                   ← reusable HTML snippets
```

## Design system

Every page links `/shared/css/nanoco-design-system.css`. Brand tokens:

| Token            | Value     |
|------------------|-----------|
| `--nc-bg`        | `#000000` |
| `--nc-panel`     | `#181818` |
| `--nc-primary`   | `#56EDD6` |
| `--nc-accent`    | `#E85D3A` |
| `--nc-text`      | `#FFFFFF` |
| `--nc-text-muted`| `#B0B0B0` |
| Font             | Inter     |

## Branch strategy

- `main` — production. Auto-deploys to the Vercel production URL.
- Feature branches — every push gets its own Vercel preview URL.
- PRs into `main` show their preview URL in the PR checks.

## Local preview

```bash
# any static server works; for example:
npx serve .
```
