# Changelog

The releases of `.github`.

Every repository of the project carries the same version and is tagged at the same moment, even where nothing changed, so an entry here may say that nothing was built. [Versioning](https://agentiik.github.io/docs#versioning) sets out why, and what a version promises before and after `1.0.0`.

`0.y.z` promises nothing beyond itself: what a release here describes may be gone in the next one.

## v0.1.1, 2026-09-13

This file, and nothing else.

`v0.1.0` was tagged before its changelog was written, and the fix for that is not to move the tag. Within minutes of the push, `sum.golang.org` had recorded the tagged commit of `agentiik` and `bricks` in a public append-only log and `proxy.golang.org` had cached it, so moving `v0.1.0` would have left `go get` serving the old code for ever and made a direct fetch fail with a checksum mismatch that reads as a supply-chain attack. A tag is a name somebody else pins, and a name that quietly comes to mean something else is worse than a second name.

So `v0.1.0` stays exactly where it is, describing exactly what it shipped, and this release adds the description. Every repository gets it at the same version on the same day, as every release here does. From now on a version's entry is merged before its tag is placed, which is written down in the conventions the documentation fixes.

## v0.1.0, 2026-09-12

What every repository shares, and the first release in which it is public.

The security policy, the code of conduct, the contribution guide, the licensing note and the trademark note live here and are pointed at from the other eleven. So does `CLAUDE.md`, the working instructions distributed to every repository, which is edited here and nowhere else.

The licence split is set out in `LICENSING.md` and is the reason this repository exists as something other than a formality: copyleft where the server lives, permissive everywhere a third party has to embed something, and a brick is not a derivative work of the engine.

Private vulnerability reporting is on across the organisation from this release, which is the channel the security policy tells a reporter to use.
