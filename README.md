## Summary

Importing a path-aliased JS module into a TS file does not correctly transpile on build.

Run `npm run build` to reproduce.

## Details

Observe `working/ts` importing `working/js` (a typescript file) via `@/working/js`.  In `dist/working/ts`, it has correctly been transpiled to `./js`

In `notworking/ts`, importing `working/js` (a javascript file) via `@/notworking/js`.  In `dist/notworking/ts`, it has not been transpiled at all and remains `@/notworking/js`, throwing an error if ran.
