# Terms

[![exist-db CI](https://github.com/HistoryAtState/terms/actions/workflows/build.yml/badge.svg)](https://github.com/HistoryAtState/terms/actions/workflows/build.yml)

A database of terms drawn from the lists of terms and abbreviations in many volumes of the *Foreign Relations of the United States*. The application provides a searchable list of all entries. 

## Data sources

- [The *Foreign Relations of the United States (FRUS)* series](https://history.state.gov/historicaldocuments) (see raw data at the [HistoryAtState/frus](https://github.com/HistoryAtState/frus) GitHub repository)

## Status

The data and app are very preliminary and subject to reorganization.

## Dependencies

- The data in the `data` collection is XML
- The application runs in [eXist](http://exist-db.org). Requires 3.0+.
- Building the installable package requires Apache Ant

## Installation

- Check out the repository
- Build the `xar` file(s) with following command:
    1. Single `xar` file: The `collection.xconf` will only contain the index, not any triggers!

      ```shell
      ant
      ```

      1. Since Releases have been automated when building locally you might want to supply your own version number (e.g. `X.X.X`) like this:

      ```shell
      ant -Dapp.version=X.X.X
      ```

## Release

Releases for this data package are automated. Any commit to the `master` branch will trigger the release automation.

All commit message must conform to [Conventional Commit Messages](https://www.conventionalcommits.org/en/v1.0.0/) to determine semantic versioning of releases, please adhere to these conventions, like so:

| Commit message  | Release type |
|-----------------|--------------|
| `fix(pencil): stop graphite breaking when too much pressure applied` | Patch Release |
| `feat(pencil): add 'graphiteWidth' option` | ~~Minor~~ Feature Release |
| `perf(pencil): remove graphiteWidth option`<br/><br/>`BREAKING CHANGE: The graphiteWidth option has been removed.`<br/>`The default graphite width of 10mm is always used for performance reasons.` | ~~Major~~ Breaking Release |

When opening PRs commit messages are checked using commitlint.