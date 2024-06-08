Renovate Repro for https://github.com/renovatebot/renovate/discussions/29539

SHOULD:

Update `windows` from `v0.56.0` to `v0.57.0`. Adding a new entry for `windows v0.57.0` to the `Cargo.lock` and keeping the `windows v0.56.0` entry for `tauri-winrt-notification v0.2.1` (As happens when running `cargo check` for instance).

ACTUAL:
https://github.com/davidkna/repro-renovate-lockfile-update/pull/3

```
Command failed: cargo update --config net.git-fetch-with-cli=true --manifest-path Cargo.toml --package windows@0.56.0 --precise 0.57.0
    Updating crates.io index
error: failed to select a version for the requirement `windows = "^0.56"`
candidate versions found which didn't match: 0.57.0
location searched: crates.io index
required by package `tauri-winrt-notification v0.2.1`
    ... which satisfies dependency `tauri-winrt-notification = "=0.2.1"` (locked to 0.2.1) of package `repro-renovate-lockfile-update v0.1.0 (/tmp/renovate/repos/github/davidkna/repro-renovate-lockfile-update)`
perhaps a crate was updated and forgotten to be re-vendored?

```
