# Security policy

This policy covers every repository in the `agentiik` organisation.

## Reporting a vulnerability

Report it privately, not in a public issue. Use **Report a vulnerability** under the
Security tab of the affected repository, which opens a private advisory visible only to
the maintainers. If you cannot reach that form, contact François Rousselet through
<https://github.com/frousselet> and ask for a private channel before sending any detail.

A report is most useful when it names the affected component and version, what an
attacker gains, and the smallest sequence that reproduces it. A proof of concept helps
and is never required.

## What happens next

| | |
| --- | --- |
| Acknowledgement | Within 3 working days. |
| First assessment | Within 10 working days: whether it is accepted, and the severity. |
| Coordinated disclosure | 90 days from acknowledgement, or the day a fix ships, whichever comes first. |

A shorter window applies to a vulnerability already being exploited. A longer one is
possible where a fix cannot be made safely in time, and is agreed with the reporter
rather than announced to them.

Advisories are published against the affected repository, with an identifier assigned
where one is warranted, and name the component, because the component is what decides
whether an installation was exposed. The fixed version is one number for the project as a
whole: every repository carries the same version and is tagged at the same moment, so
there is no per-component version for an advisory to name. Reporters are credited by the
name they ask for, or not at all if they prefer.

## Supported versions

The most recent release is what is supported. While the project is at `0.y.z` it is the
most recent `0.y.z`, and a fix ships in the next release rather than as a patch to an
older one: <https://agentiik.github.io/docs#versioning> sets out what a `0.y.z` release
promises, which is nothing beyond itself. That changes at `1.0.0`.

The default branch is where a fix lands first, and it is not a release.

## Scope

In scope: the code in this organisation's repositories, the images published to
`ghcr.io/agentiik`, and the workflows that build them.

Out of scope: findings against GitHub itself, against a third-party dependency where the
right place to report is that project, and reports consisting only of a scanner's output
with no demonstrated impact. Denial of service through resource exhaustion on a
self-hosted installation is out of scope where it is the documented consequence of a
quota the operator set.

## What the security model already says

The specification is explicit that `workflow:write` is arbitrary code execution: a
workflow names container images and shell commands, so anyone able to push to a workflow
repository can run code of their choosing inside a container on a runner in that
namespace's pools. That is the product, not a vulnerability. A way to escape the
container, to read another namespace's secrets or artifacts, or to obtain a grant beyond
the task's own, is a vulnerability. The distinction is set out at
<https://agentiik.github.io/docs>.
