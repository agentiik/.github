# Contributing

This guide covers every repository in the `agentiik` organisation.

The project is unreleased and the specification is ahead of the code. The most useful
contribution right now is an argument against something in the specification at
<https://agentiik.github.io/docs> — a case it does not handle, a boundary drawn in the
wrong place, a decision that will cost more later than it saves now.

## Before a pull request

Open an issue first for anything that changes behaviour, the workflow language, the brick
contract, the API or the permission model. A rejected design is cheaper as a paragraph
than as a branch. Typos, broken links and obvious bugs need no issue.

A change to the workflow format starts in
[`agentiik/schemas`](https://github.com/agentiik/schemas) and is released there before
anything else consumes it. Nothing else redefines those shapes.

## The Developer Certificate of Origin

Every commit carries a `Signed-off-by` line, which `git commit -s` adds:

```
Signed-off-by: Your Name <your.email@example.com>
```

That line means you certify the [Developer Certificate of Origin
1.1](https://developercertificate.org/): the work is yours to submit under this
repository's licence. There is no contributor licence agreement, and you keep the
copyright in your patch. [LICENSING.md](LICENSING.md) explains what that choice costs and
why it was made anyway.

Use a name you are willing to be credited under. A pseudonym is fine; an anonymous
sign-off is not, because the DCO is an attestation and an attestation needs somebody
making it.

## Conventions

- Default branch `main`. Branch from it, rebase onto it, and keep a pull request to one
  concern.
- All documentation and code, including comments, identifiers and commit messages, are
  written in **English**.
- Commit messages say what the change does and why, in the imperative. The body is where
  the reasoning goes; a message with no body is fine when there is no reasoning to give.
- Chapters and sections are never numbered.
- An identifier that appears in YAML, in the API and on screen is the same string in all
  three. Never translate or prettify one.
- Documentation lives at <https://agentiik.github.io>, not scattered through the
  repositories. Each repository keeps only a short README pointing there, so that a
  reader never has to guess which copy is current.

## Review

Every change arrives through a pull request, including a maintainer's own. What review
looks for, in order: whether the change is the right one to make, whether it holds at the
boundaries, whether it fits what the specification says, and only then whether the code
reads well.

## Security

Never open a public issue for a vulnerability. [SECURITY.md](SECURITY.md) says what to do
instead.

## Conduct

[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) applies everywhere in this organisation.
