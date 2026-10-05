# rustc-auto-publish

Repository for automatically publishing the crates below every Sunday.

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

## Manual publishing

This is sometimes needed when an automatically published version doesn't build
in rust-analyzer (see e.g. https://github.com/rust-lang/rust/pull/160164).

The solution we use is to create a fork of rust-lang/rust, apply patches on
affected versions, and point the auto-publishing script to that repo+commit.

On CI, this is done by running the **CI** workflow manually with:
- `repo_override` set to the GitHub repository in `owner/repo` form (blank
defaults to `rust-lang/rust`)
- `sha_override` set to the commit SHA (blank defaults to selected repository's
`HEAD`)
- `version_override` set to the version to publish as (blank defaults to the
next minor version)

This publishes the usual `ra-ap_*` crates with the selected version.
