# rustc-auto-publish

Repository for automatically publishing the crates below every Sunday.

To publish from a fork at a specific revision, run the **CI** workflow manually
with `repo_override` set to the GitHub repository in `owner/repo` form and
`sha_override` set to the commit SHA. Blank inputs default to `rust-lang/rust`
and the selected repository's `HEAD`, respectively. Scheduled and push runs
continue to use `rust-lang/rust` at `HEAD`.

These overrides select the Rust sources, not the publishing script. They publish
the usual `ra-ap_*` crates with the next version; they do not create a separate
fork-specific release channel. Only select trusted fork revisions: publishing
can execute code from the selected sources while registry credentials are available.

The same overrides can be supplied locally as optional positional arguments:

```sh
cargo run -- publish <github-token> <owner/repo> <commit-sha>
```

Use `nopublish` instead of `publish` to inspect the dependency graph without
publishing crates.

- [ra-ap_rustc_abi][ra-ap_rustc_abi-crate] [![ra-ap_rustc_abi version][ra-ap_rustc_abi-version-badge]][ra-ap_rustc_abi-crate]
- [ra-ap_rustc_index][ra-ap_rustc_index-crate] [![ra-ap_rustc_index version][ra-ap_rustc_index-version-badge]][ra-ap_rustc_index-crate]
- [ra-ap_rustc_lexer][ra-ap_rustc_lexer-crate] [![ra-ap_rustc_lexer version][ra-ap_rustc_lexer-version-badge]][ra-ap_rustc_lexer-crate]
- [ra-ap_rustc_macros][ra-ap_rustc_macros-crate] [![ra-ap_rustc_macros version][ra-ap_rustc_macros-version-badge]][ra-ap_rustc_macros-crate]
- [ra-ap_rustc_parse_format][ra-ap_rustc_parse_format-crate] [![ra-ap_rustc_parse_format version][ra-ap_rustc_parse_format-version-badge]][ra-ap_rustc_parse_format-crate]
- [ra-ap_rustc_pattern_analysis][ra-ap_rustc_pattern_analysis-crate] [![ra-ap_rustc_pattern_analysis version][ra-ap_rustc_pattern_analysis-version-badge]][ra-ap_rustc_pattern_analysis-crate]
- [ra-ap_rustc_serialize][ra-ap_rustc_serialize-crate] [![ra-ap_rustc_serialize version][ra-ap_rustc_serialize-version-badge]][ra-ap_rustc_serialize-crate]

[ra-ap_rustc_abi-crate]: https://crates.io/crates/ra-ap_rustc_abi
[ra-ap_rustc_abi-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_abi?style=flat-square
[ra-ap_rustc_index-crate]: https://crates.io/crates/ra-ap_rustc_index
[ra-ap_rustc_index-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_index?style=flat-square
[ra-ap_rustc_lexer-crate]: https://crates.io/crates/ra-ap_rustc_lexer
[ra-ap_rustc_lexer-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_lexer?style=flat-square
[ra-ap_rustc_macros-crate]: https://crates.io/crates/ra-ap_rustc_macros
[ra-ap_rustc_macros-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_macros?style=flat-square
[ra-ap_rustc_parse_format-crate]: https://crates.io/crates/ra-ap_rustc_parse_format
[ra-ap_rustc_parse_format-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_parse_format?style=flat-square
[ra-ap_rustc_pattern_analysis-crate]: https://crates.io/crates/ra-ap_rustc_pattern_analysis
[ra-ap_rustc_pattern_analysis-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_pattern_analysis?style=flat-square
[ra-ap_rustc_serialize-crate]: https://crates.io/crates/ra-ap_rustc_serialize
[ra-ap_rustc_serialize-version-badge]: https://img.shields.io/crates/v/ra-ap_rustc_serialize?style=flat-square
