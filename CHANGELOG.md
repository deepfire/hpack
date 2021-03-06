## Changes in 0.27.0
  - Local defaults are now resolved relative to the file they are
    mentioned in, not the CWD that hpack is invoked from.

## Changes in 0.26.0
  - Major refactoring of the exposed API (much cleaner now, but lot's of
    breaking changes!)
  - Remove Git conflict markers before checking the hash of any existing
    `.cabal` files (equivalent to `git checkout --ours`).  This allows to
    regenerate the `.cabal` file on conflicts when rebasing without passing
    `-f` in some cases and helps with preserving the formatting.
  - Allow local files to be used as defaults (#248)

## Changes in 0.25.0
  - Keep non-existing literal files on glob expansion (see #101)

## Changes in 0.24.0
  - Add support for `verbatim` Cabal escape hatch
  - Allow `version` be a numbers
  - Ignore fields that start with an underscore everywhere, not just globally

## Changes in 0.23.0
  - Add support for custom decoders to allow for alternate syntax (e.g. Dhall)
  - `generated-exposed-modules` and `generated-other-modules`, for populating
    the `autogen-modules` field (#207).
  - Corrected `cabal-version` setting for `reexported-modules` inside
    a conditional.

## Changes in 0.22.0
  - Add support for `defaults`
  - Add `--numeric-version`
  - Add support for `signatures`
  - `extra-doc-files` requires setting `cabal-version` to at least
    1.18; this is now done properly.
  - Accept bool for `condition` (see #230)

## Changes in 0.21.2
  - Fix a bug in module inference for conditionals (see #236)
  - Add support for `extra-doc-files`.
  - Add support for `pkg-config-dependencies`

## Changes in 0.21.1
  - Allow dependency constraints to be numbers (see #234)

## Changes in 0.21.0
  - Accept section-specific fields in conditionals (see #175, thanks to Scott
    Fleischman)
  - New section: `internal-libraries`, for Cabal 2's internal libraries (see #200).

## Changes in 0.20.0
  - Do not overwrite any existing cabal file if it has been modified manually

## Changes in 0.19.3
  - Add support for `frameworks` and `extra-frameworks-dirs`

## Changes in 0.19.2
 - Compatibility with `Glob >= 0.9.0`

## Changes in 0.19.1
  - Add `IsList` instance for `Dependencies`

## Changes in 0.19.0
  - Add Paths_* module to executables (see #195, for GHC 8.2.1 compatibility)
  - Allow specifying dependencies as a hash (see #198)

## Changes in 0.18.1
  - Output generated cabal file to `stdout` when `-` is given as a command-line
    option (see #113)
  - Recognize `.chs`, `.y`, `.ly` and `.x` as Haskell modules when inferring
    modules for

## Changes in 0.18.0
  - Make `executable` a shortcut of `executables: { package-name: ... }`
  - Add support for `ghcjs-options` and `js-sources` (see #161)
  - Allow `license-file` to be a list
  - Accept input file on command-line (see #106)
  - Add Paths_* when no modules are specified (see #86)

## Changes in 0.17.1
  - Do not descend into irrelevant directories when inferring modules (see #165)

## Changes in 0.17.0
  - Added custom-setup section
  - Add support for `!include` directives

## Changes in 0.16.0
  - Warn when `name` is missing
  - Support globs in `c-sources`
  - Use binary I/O for cabal files avoiding problems with non-UTF-8 locales
  - Fix rendering of `.` as directory (cabal syntax issue)
