# Licensing

One licence across an organisation is the tidy answer and the wrong one. What a
repository is for decides what its licence has to allow, and these repositories are for
two different things: one of them is a server somebody might host, the rest are things
other people must embed in their own work.

Every licence here is OSI-approved. Every repository carries its own `LICENSE` file, and
that file, not this page, is the licence.

## The split

| Repository | Licence | Why |
| --- | --- | --- |
| [agentiik](https://github.com/agentiik/agentiik)<br>[console](https://github.com/agentiik/console)<br>[ios](https://github.com/agentiik/ios)<br>[android](https://github.com/agentiik/android) | AGPL-3.0-or-later | These are the service. Section 13 requires that anyone who modifies the program and offers it to users over a network offer those users the corresponding source. That is the only OSI-approved answer to somebody selling a modified Agentiik as a hosted product, and it asks nothing at all of an organisation running an unmodified build for itself. |
| [schemas](https://github.com/agentiik/schemas)<br>[brick-sdk](https://github.com/agentiik/brick-sdk)<br>[bricks](https://github.com/agentiik/bricks) | Apache-2.0 | Everything here ends up inside somebody else's brick or client. Copyleft would reach into work that has nothing to do with the engine, which is the opposite of the goal: anyone must be able to write a brick, in any language, under any licence. |
| [deploy](https://github.com/agentiik/deploy)<br>[.github](https://github.com/agentiik/.github) | Apache-2.0 | Configuration and templates people copy into their own infrastructure. |
| [design](https://github.com/agentiik/design)<br>[agentiik.github.io](https://github.com/agentiik/agentiik.github.io) | Apache-2.0 for code<br>CC BY 4.0 for assets and prose | Tokens and icons are code; documentation and the specimen sheet are not, and a software licence is a poor fit for either when the other is what someone wants to reuse. |

One alternative deserves to be weighed rather than listed as rejected: Apache-2.0 across
every repository. That is the right answer if adoption inside organisations which ban the
AGPL by policy matters more than preventing a third party from selling a hosted Agentiik.
No OSI-approved licence gives both, so the split above is a choice about which of the two
the project would rather give up.

## A brick is not a derivative work of the engine

The two exchange a JSON envelope on standard input and output, files under `/agk/in` and
`/agk/out`, and an exit code, across a process and a container boundary, with no shared
address space and no linking of any kind.

The Free Software Foundation's own guidance is that "pipes, sockets and command-line
arguments are communication mechanisms normally used between two separate programs. So
when they are used for communication, the modules normally are separate programs."

So: a brick you write carries whatever licence you choose, and running it on Agentiik
imposes nothing on it. This is stated up front because it removes the one objection that
would otherwise keep the AGPL out of the conversation, and it costs nothing, because it
is simply what the brick contract already is.

## Contributions

Contributions are accepted under the [Developer Certificate of Origin
1.1](https://developercertificate.org/), with a `Signed-off-by` line, not under a
contributor licence agreement. The DCO is an attestation of provenance: the contributor
certifies the work is theirs to submit under the project's licence. It is not a grant of
rights to the maintainer.

That choice is deliberate and it has a cost worth naming: without a CLA, nobody can
relicense the project later, because every contributor keeps the copyright in their own
patch. A project that intends to sell a differently licensed edition one day needs a CLA
from its first commit, and cannot bolt one on afterwards without tracking down every
contributor.

`AGPL-3.0-or-`*`later`* rather than `-only` for the same reason: with no CLA, the "or
later" clause is the one migration path a maintainer keeps.

## What was not chosen

| Option | Why not |
| --- | --- |
| Business Source License 1.1 | Not an open source licence. It converts to a GPL-2.0-compatible Change License on the stated Change Date or "the fourth anniversary of the first publicly available distribution", whichever comes first, but a delayed conversion is still a period during which the software is not open source. Leaving a source-available licence behind is part of why this project exists. |
| SSPL, Elastic License 2.0 | Neither appears on the OSI-approved list. The same objection as above, without the conversion that at least gives the BUSL an end date. |
| MIT, BSD-2-Clause, BSD-3-Clause | No express patent grant. Apache-2.0 asks nothing more of anyone and its section 3 grants one, so the permissive half of the split goes to Apache rather than to a shorter licence. |
| A contributor licence agreement | It would keep the option of relicensing or of a differently licensed edition, at the price of a barrier in front of every drive-by contribution. Worth revisiting only alongside a decision to sell something, and only before the first outside patch lands. |

## The name

None of this covers the name or the mark: a licence governs copyright, not a trademark.
See [TRADEMARK.md](TRADEMARK.md).
