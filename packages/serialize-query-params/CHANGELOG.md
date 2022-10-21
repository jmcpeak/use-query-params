# Changelog

## serialize-query-params v2.0.2

**Fixes**
- `updateLocation` returns an empty string for `href` when the original `location.href` is not defined. This allows `updateLocation` to be recursively recalled without crashing when creating a `new URL()`  (#244)

## serialize-query-params v2.0.1

**Fixes**
- type for urlName is now string (#227)

## serialize-query-params v2.0.0

**Breaking**

- Drop dependency for [query-string](https://github.com/sindresorhus/query-string). You now must pass your stringify/parse functions directly to `updateLocation` and `updateInLocation`.

**New Features**

- `objectToSearchString` - small wrapper around URLSearchParams that handles undefined, null, and array values. A lesser version of query-string’s “stringify”
- `searchStringToObject` - small wrapper around URLSearchParams that handles array values. A lesser version of query-string’s “parse”
- Adds new `createEnumArrayParam` and `createEnumDelimitedArrayParam` helpers
- Adds `default` and `urlName` as optional attributes of a Parameter, mostly for other tooling to introspect on. Note that `withDefault` now populates the `default` attribute.
