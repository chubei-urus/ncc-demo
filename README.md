# Build fails with `composite: true`

```bash
npm i
cd app
npm run build
```

Output:

```text
> app@1.0.0 build
> ncc build main.ts

ncc: Version 0.38.1
ncc: Compiling file index.js into ESM
ncc: Using typescript@5.6.2 (local user-provided)
Error: [tsl] ERROR in C:\Users\91474\urus\ncc-demo\app\main.ts(1,23)
      TS6059: File 'C:\Users\91474\urus\ncc-demo\lib\index.ts' is not under 'rootDir' 'C:/Users/91474/urus/ncc-demo/app'. 'rootDir' is expected to contain all source files.
  The file is in the program because:
    Imported via 'lib/index' from file 'C:/Users/91474/urus/ncc-demo/app/main.ts'
    Root file specified for compilation
    at C:\Users\91474\urus\ncc-demo\node_modules\@vercel\ncc\dist\ncc/index.js.cache.js:38:1896272
    at C:\Users\91474\urus\ncc-demo\node_modules\@vercel\ncc\dist\ncc/index.js.cache.js:38:396262
    at _done (eval at create (C:\Users\91474\urus\ncc-demo\node_modules\@vercel\ncc\dist\ncc/index.js.cache.js:21:75523), <anonymous>:9:1)
    at eval (eval at create (C:\Users\91474\urus\ncc-demo\node_modules\@vercel\ncc\dist\ncc/index.js.cache.js:21:75523), <anonymous>:34:22)
npm ERR! Lifecycle script `build` failed with error: 
npm ERR! Error: command failed
npm ERR!   in workspace: app@1.0.0
npm ERR!   at location: C:\Users\91474\urus\ncc-demo\app
```

# Build succeeds with `composite: false`

In `app`:

```bash
git apply ../composite-false.patch
npm run build
```

Output:

```text
> app@1.0.0 build
> ncc build main.ts

ncc: Version 0.38.1
ncc: Compiling file index.js into ESM
ncc: Using typescript@5.6.2 (local user-provided)
0kB  dist\package.json
0kB  dist\index.js
0kB  [1362ms] - ncc 0.38.1
```
