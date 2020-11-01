# [![Build Status][travis-image]][travis-url] [![Coverage Status][coveralls-image]][coveralls-url]

## conventionalcommits.org convention

A concrete implementation of the specification described at
[conventionalcommits.org](https://conventionalcommits.org/) for automated
CHANGELOG generation and version management.

## FORK WARNING

This is a fork of `conventional-changelog-conventionalcommits` with my proposed changes.
The fork may or may not be kept up-to-date with upstream and will with most certanty be abandoned if upstream merges pull requests.
Use with caution.

List of propsed pull requests:

* [PR-669: allow matching scope](https://github.com/conventional-changelog/conventional-changelog/pull/669)

## Indirect Usage (as preset)

Use the [Conventional Changelog CLI Quick Start](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-cli#quick-start) with the `-p conventionalcommits` option.

## Direct Usage (as a base preset so you can customize it)

If you want to use this package directly and pass options, you can use the [Conventional Changelog CLI Quick Start](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-cli#quick-start) and with the `--config` or `-n` parameter, pass a js config that looks like this
```
'use strict'
const config = require('conventional-changelog-conventionalcommits')

module.exports = config({
    "issuePrefixes": ["TEST-"],
    "issueUrlFormat": "myBugTracker.com/{prefix}{id}"
})
```

or json config like that:
```
{
    "options": {
        "preset": {
            "name": "conventionalchangelog",
            "issuePrefixes": ["TEST-"],
            "issueUrlFormat": "myBugTracker.com/{prefix}{id}"
        }
    }
}
```
This last json config way passes the `preset` object to the `conventional-changelog-preset-loader` package, that in turn, passes this same `preset` object as the config for the `conventional-changelog-conventionalcommits`.



See [conventional-changelog-config-spec](https://github.com/conventional-changelog/conventional-changelog-config-spec) for available
configuration options.


[travis-image]: https://travis-ci.org/conventional-changelog/conventional-changelog.svg?branch=master
[travis-url]: https://travis-ci.org/conventional-changelog/conventional-changelog
[coveralls-image]: https://coveralls.io/repos/conventional-changelog/conventional-changelog/badge.svg
[coveralls-url]: https://coveralls.io/r/conventional-changelog/conventional-changelog
