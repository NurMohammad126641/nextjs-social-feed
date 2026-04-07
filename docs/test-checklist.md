# Manual test checklist

Automated in CI on every push: `npm ci`, `npm run lint`, `npm run typecheck`,
`prisma migrate deploy`, `npm run build`, and a gitleaks secret scan.

Manual checks before a release:

- [ ] `npm run db:setup` completes and the demo accounts can log in
- [ ] Logged-out `/feed` redirects to `/login`
- [ ] Registration, login and logout work
- [ ] Public posts are visible to other users
- [ ] Private posts are visible only to their author
- [ ] Image upload works; wrong file types and files over 5 MB are rejected
- [ ] Feed is newest first
- [ ] Post, comment and reply likes toggle correctly
- [ ] Liked-by lists show the right users
- [ ] Invalid input shows clear validation errors
- [ ] No secrets or local files (`.env`, `*.db`, `public/uploads`) are tracked
