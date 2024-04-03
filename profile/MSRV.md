# Ardaku MSRV Policy

The Ardaku MSRV policy applies to all crates in the Ardaku organization, and can be used elsewhere.

It attempts to strike a balance between maintainers on newer versions and consumers on older versions.

## Version 0.0.z

Anything goes.
Latest Rust only.

## Version 0.x.y

Active changes, short term Rust version support (about 6 months - 24-30+ weeks).
The fourth previous release from current Rust is the maximum MSRV of the crate.
MSRV may only be increased on minor version bumps.
MSRV may be decreased on patch version bumps.
Only the most recent minor version is maintained.

Example:

 - 1.81 - Current Rust
 - 1.80
 - 1.79
 - 1.78
 - 1.77 - Highest MSRV the crate can have

## Version x.y.z

Project is considered "complete" in API design and cross-platform testing.
Similary, the fourth previous release from current Rust is the maximum MSRV of the crate.
Long term Rust version support on x.0.z (1.5+ years).
MSRV may only be changed on minor version bumps.
MSRV may be decreased on patch version bumps.
Each minor version is maintained at least until its chosen version of Rust is over 1.5 years old (for 13 Rust versions).
Editions chosen should always be the latest for that version of Rust.
Major versions should correspond with minimum edition bumps.

 - 1.77 - Highest MSRV the crate can have
 - 1.81 - Current Rust
 - 1.90 - MSRV 1.77 versions must be supported at least until this release

## Minimum MSRV

New MSRVs can be less than what is specified above, but shouldn't go below Rust 1.65.
This will be increased in the future, but how that's decided is currently unspecified.

## When To Update MSRV

MSRV should be updated in the following situations:

 - Dependency updated MSRV in new version
 - Clippy lints on current Rust request a std api be used that's only available in a more recent Rust
 - New edition release
 - New feature in more recent Rust simplifies code

## When Dependencies Have More Aggresive MSRV

Depending on an old unmaintained version is fine, as long as there are no security vulnerabilities.
Although, it should be updated when possible.

If there is a security vulnerability that can't be updated within these guidelines,
an alternative crate should be used in affected versions, if not all versions.
