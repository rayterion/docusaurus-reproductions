## The bug

PR: #10855

When linking to a JS file in markdown, the build actually fails.

```bash
> yarn build
yarn run v1.22.22
$ docusaurus build
[INFO] [en] Creating an optimized production build...

✖ Client
  Compiled with some errors in 44.12s

✔ Server
  

[ERROR] Client bundle compiled with errors therefore further build is impossible.
assets/files/test-7fc106457f8b61bbbba06a8405ca0adb.js from Terser plugin
Unexpected line terminator [assets/files/test-7fc106457f8b61bbbba06a8405ca0adb.js:2,undefined]
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```

## expected behavior

```bash
yarn build
yarn run v1.22.22
$ docusaurus build
[INFO] [en] Creating an optimized production build...

✔ Client
  Compiled successfully in 2.66s

✔ Server
  


● Client █████████████████████████ cache (99%) shutdown IdleFileCachePlugin
 serialize pack

● Server █████████████████████████ cache (99%) shutdown IdleFileCachePlugin
 stored

[SUCCESS] Generated static files in "build".
[INFO] Use `npm run serve` command to test your build locally.
Done in 6.17s.
```

## workaround
`[Test](pathname://misc/test.js)` instead of `[Test](/misc/test.js)`

## Installation

```bash
yarn
```

## Local Development

```bash
yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

## Build

```bash
yarn build
```