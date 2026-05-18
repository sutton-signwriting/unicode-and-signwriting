# Package and Tooling Notes

**Where `@sutton-signwriting/unicode8` fits**

## Why the package exists

Official Unicode SignWriting exists in the world.

Developers therefore still need tooling to:

- process Unicode 8 SignWriting characters
- inspect them
- convert them
- compare them with FSW and SWU
- support mixed environments where official Unicode characters appear

That is what a package such as `@sutton-signwriting/unicode8` is for.

The package exists because naming official characters is still a practical need even when stable symbol identity and written-sign support remain unresolved.

## What the package does not mean

The existence of the package does **not** mean:

- official Unicode SignWriting is accepted as the best canonical production path
- the broader compatibility problem is solved
- character naming automatically preserves stable symbols
- spatial composition is no longer an issue
- FSW and SWU have become unnecessary

Developers still need competent tooling for a standard that exists publicly, even when that standard is still insufficient.

## Useful links

These links are repeated here for readers who enter through this companion note rather than the main Developer Notes entry.

- [Source](https://github.com/sutton-signwriting/unicode8)
- [Distribution](https://unpkg.com/browse/@sutton-signwriting/unicode8/)
- [Documentation](https://sutton-signwriting.github.io/unicode8/)
- [Issue Tracker](https://github.com/sutton-signwriting/unicode8/issues)

## Short description

`@sutton-signwriting/unicode8` is a JavaScript package for processing official Unicode SignWriting characters, from the model introduced in Unicode 8.0.0, while also supporting FSW and SWU in the same broader technical ecosystem.

It is a bridge and processing library.

It helps software deal with official Unicode SignWriting where that standard appears in the world.

It does not mean that character naming, stable symbol identity, and written-sign encoding have all been solved by the same model.
