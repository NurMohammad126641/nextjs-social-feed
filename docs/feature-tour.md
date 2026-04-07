# Feature tour

A five-minute walkthrough of the app using the seeded demo accounts
(`npm run db:setup` creates them).

1. **Protected routes.** While logged out, open `/feed`. You are redirected to `/login`.
2. **Sign in.** Log in as `jane@example.com` / `Password123`. The session is a signed JWT
   in an `httpOnly` cookie.
3. **Feed.** Posts are newest first. Jane can see her own private post; other users cannot.
4. **Create a public post.** Write some text, attach an image and post it. It appears at the
   top of the feed.
5. **Create a private post.** Switch visibility to private. The card shows a private label.
6. **Reactions.** Like and unlike a post, then open the liked-by list to see who reacted.
7. **Conversations.** Comment on a post, reply to the comment, like both, and open their
   liked-by lists.
8. **Visibility check.** Log out, log in as `alex@example.com` / `Password123`. Public posts
   are there; Jane's private post is not.
9. **Registration.** Log out and create a new account (first name, last name, email,
   password).

Where to look in the code:

- `prisma/schema.prisma`: data model
- `lib/auth.ts`: password hashing, session cookies, `requireUserId()`
- `lib/feed.ts`: feed query with visibility filtering and comment-tree shaping
- `app/api/posts/route.ts`, `app/api/comments/route.ts`: write paths and access checks
