# gist-publish-npm

Publish a Gist to npm as a scoped package.

```
npm install -g gist-publish-npm
```

## Usage

```
gist-publish-npm [gist-id, ...] [config]
```

Positional args are Gist IDs to publish, flags will be passed verbatim as [npm config vars](https://docs.npmjs.com/misc/config).

## This tool assumes:

 - You've already run `npm login`, or you trust me with your npm login deets and can work out how the pass them in
 - Your Gist has a single `.js` file
   - That should be the entry point of the module
   - Whose basename should be the name of the module
 - Your Github username is a reasonable thing to use as the [package scope](https://docs.npmjs.com/misc/scope)
 - The last committer to the Gist is a reasonable thing to use as the package author

## Package versions

Your Gist will be published with the version `1.<number of commits minus one>.0`. A Gist with one commit is thus published as `1.0.0`.

## Dependencies

Any `require` calls in your main will be added top `package.json` as dependencies, with `*` as the version. Sorry.

## Licence

MIT.
