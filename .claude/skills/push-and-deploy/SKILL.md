---
name: push-and-deploy
description: Use when the user asks to commit and push to git and publish/deploy to Vercel production for this project. Triggers on phrases like "git push y publica en vercel", "push and deploy", "publicar cambios", "subir y desplegar".
---

# Push and Deploy

Commit, push to GitHub, and deploy to Vercel production in one step.

## Steps

1. Invoke **git-workflow:git-push** — it handles staging, commit message generation, and push to `main`.
2. Once the push completes, run:

```bash
vercel --prod --yes
```

3. Report the final production URL from the Vercel output.

## Notes

- Always deploy to production (`--prod`), never preview.
- No confirmation needed — the user expects both steps to run end-to-end.
- If git-workflow:git-push finds nothing to commit (clean tree), skip to the Vercel deploy anyway.
