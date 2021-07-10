# kit-pirms-ssr-bug

Repro for a bug: https://github.com/pngwn/prism-svelte/issues/11

## run it

```bash
pnpm i
pnpm dev
```

Navigate to `http://localhost:3000`.

When loading a page this produces:

```
Cannot read property 'highlight' of undefined
```

Because `Prism` is undefined.

This works:

```bash
pnpm build
pnpm preview
```

Navigate to `http://localhost:3000`.

No problem, everything highlighted.

## why?

No idea. It will be something to with PrismJS's UMD output (attaching itself to the global namespace) and the way vite bundles for dev.
