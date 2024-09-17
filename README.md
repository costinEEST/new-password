# Docs 

- [Readme](./docs.md)
- https://tailwindcss.com/docs/guides/sveltekit
- https://www.okupter.com/blog/deploy-sveltekit-website-to-github-pages, https://www.youtube.com/watch?v=jBSnjlp-ZYw

# Setup 

```bash
pnpm create svelte@latest password-generator


create-svelte version 6.3.8

┌  Welcome to SvelteKit!
│
◇  Which Svelte app template?
│  Library project
│
◇  Add type checking with TypeScript?
│  Yes, using TypeScript syntax
│
◇  Select additional options (use arrow keys/space bar)
│  Add ESLint for code linting, Add Prettier for code formatting, Add Playwright for browser testing, Add Vitest for unit testing, Try the Svelte 5 preview (unstable!)
│
└  Your project is ready!

Install more integrations with:
  npx svelte-add

Next steps:
  1: cd password-generator
  2: pnpm install
  3: git init && git add -A && git commit -m "Initial commit" (optional)
  4: pnpm run dev -- --open

To close the dev server, hit Ctrl-C

Stuck? Visit us at https://svelte.dev/chat
```

- `pnpm install -D tailwindcss@latest postcss@latest autoprefixer@latest` then `pnpm dlx tailwindcss init -p`
- `pnpm install -D @sveltejs/adapter-static gh-pages`

