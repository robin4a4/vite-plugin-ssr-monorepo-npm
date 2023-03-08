# vite-plugin-ssr NPM monorepo issue reproduction

Logging in the `load()`function at `vite-plugin-ssr/dist/cjs/node/plugin/plugins/virtualFiles/index.js` with the following expression:

```
console.log("--> load", id)
```

## importing the local package

```
--> load virtual:vite-plugin-ssr:pageFiles:server
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/index/index.page.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/\_default.page.server.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/\_default.page.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/index/Counter.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/Layout.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/Head.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/style.css
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/\_default/Link.tsx
```

Here the `@vite-plugin-ssr-monorepo/renderer` package is not recognized.

## importing the real @brillout/stem-react package

```
--> load virtual:vite-plugin-ssr:pageFiles:server
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/index/index.page.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/_default.page.server.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/_default.page.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/node_modules/@brillout/stem-react/dist/renderer/_default.page.client.js?extractExportNames
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/index/Counter.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/Layout.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/Head.tsx
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/style.css
--> load /Users/robinmarillia/Documents/dev/lab/vite-plugin-ssr-monorepo-npm/packages/site/pages/_default/Link.tsx
```

Here the `@brillout/stem-react` package is correctly recognized.
