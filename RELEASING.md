# Releasing

Every repository of the organisation is tagged with the same version at the same moment ([Versioning](https://agentiik.github.io/docs#versioning)). A tag of `agentiik` is recorded by the Go proxy and `sum.golang.org` within minutes of being pushed, so everything below happens before the tag and nothing is fixed after it. `v0.2.0` was tagged with the documentation still describing `v0.1.2` and a Homebrew tap that had never been installed from GitHub; this list is what would have caught both.

## Before the tag

| Check | How |
| --- | --- |
| Every task of the milestone is closed, and the roadmap says so | `gh issue list --milestone vX.Y.Z --state open` is empty in all thirteen repositories; the Roadmap workflow has run and the milestone's tally reads done |
| `main` is green where it will be tagged | every check on the commit, `e2e` included, in `agentiik` |
| Nothing a reader sees names the previous release | search every repository for the previous version, `--HEAD`, "in progress", "until vX.Y.Z" and "not yet"; a statement about history stays, a statement about the present moves |
| Every terminal output on the site is the new release's | replay Get started with the release candidate of `agk`, and re-record every asciinema cast in `agentiik.github.io/assets`, the home page and the Command line transcripts with it |
| Every README's status says what the release does | `agentiik` above all: what runs, what still refuses and why |
| The documentation of everything merged is on the site | nothing left parked; the last pull request of documentation is merged |
| The vendored schemas equal the schemas repository | `internal/fixtures/testdata` of `agentiik` against `schemas` `main` |
| The API document names the release | `info.version` of the schemas repository's `openapi.json` is the version without its `v`, which is how a reader of the document knows the release it describes |
| The previous release upgrades to this one with `compose.yaml` and `.env` alone | the `upgrade` job of deploy's single-host workflow, on `main`: it installs the previous release, runs a workflow, upgrades, and checks the old token, the old run and a new run |
| Every `CHANGELOG.md` has its version's entry, and no `Unreleased` left | merged in all thirteen repositories before any tag |

## The tag

1. Tag all thirteen repositories, annotated, with the release's name from the roadmap as the message, `agentiik` first.
2. In `homebrew-tap`, point `tag` and `revision` of both formulae at the new tag (`git ls-remote https://github.com/agentiik/agentiik.git refs/tags/vX.Y.Z^{}`), merge, and move `homebrew-tap`'s own tag onto that commit if it was placed before.

## After the tag

| Check | How |
| --- | --- |
| The site serves the new release | the Publish workflow of `agentiik.github.io` does not run on a tag, and `/docs/` shows the latest tag it saw: run it from `main` (`gh workflow run publish.yml --repo agentiik/agentiik.github.io --ref main`), then load https://agentiik.github.io/docs/ and read the version Get started prints |
| The images are published | `ghcr.io/agentiik/api`, `controller`, `runner` and `postgres-upgrade` answer an anonymous pull at the version and at `latest`, on one digest |
| The single-host installation runs as written | the `single-host` workflow of `agentiik/deploy`, run on `main` after the tag, uses the published images and the README verbatim |
| The install a person does works | `homebrew-tap`'s `as-installed` job, run by the push to `main` and by the tag, installs both formulae from GitHub and checks each program names the tag |
| This machine installs what the README says | the local tap is the GitHub one (`git -C "$(brew --repo agentiik/tap)" remote -v`), then `brew update && brew upgrade agentiik/tap/agk agentiik/tap/agentiik` and `agk --version` |
| The milestone is closed and the board says Done | `v0.y.z` milestones closed in all thirteen repositories; nothing closed on the project is left in another status |
