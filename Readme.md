This package contains the core logic of Slate. Feel free to poke around to learn more!

Note: A number of source files contain extracted types for `Interfaces` or `Transforms`. This is done currently to enable custom type extensions as found in `packages/src/interfaces/custom-types.ts`.

## Why fork?

In Sling we switch original window.Promise implementation with \$q provided from angular.
Because of that slate editor's cursor lags on fast typing. To workaround that, we restore original Promise for slate:

```
const Promise = typeof window !== 'undefined' ? (window.__Promise || window.Promise) : Promise;
```