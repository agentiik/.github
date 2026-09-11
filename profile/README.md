## Agentiik

A workflow engine where a workflow is a git repository, a step is a container, and what
passes between steps is a JSON envelope. The engine hosts the repository rather than
cloning one from a forge, so a version cannot drift beneath a run, an invalid workflow
cannot be pushed at all, and repository access is the permission model that already
exists rather than a second one to reconcile with it.

The documentation (scope, the workflow language, the brick contract, access control, the
runtime, security, deployment profiles and MCP) is at **<https://agentiik.github.io/docs>**.

### Repositories

| | |
| --- | --- |
| [agentiik](https://github.com/agentiik/agentiik) | The core: graph evaluator, container driver, controller, HTTP API, runner, `agk`. |
| [schemas](https://github.com/agentiik/schemas) | The workflow, brick and envelope schemas, and the OpenAPI document. |
| [bricks](https://github.com/agentiik/bricks) | The standard catalog. |
| [brick-sdk](https://github.com/agentiik/brick-sdk) | Optional helpers for the envelope contract. |
| [design](https://github.com/agentiik/design) | Tokens, icons and the specimen sheet. |
| [console](https://github.com/agentiik/console) | The web console. |
| [ios](https://github.com/agentiik/ios) · [android](https://github.com/agentiik/android) | The mobile applications. |
| [deploy](https://github.com/agentiik/deploy) | Compose stacks, installer, migration notes. |
| [terraform-provider-agentiik](https://github.com/agentiik/terraform-provider-agentiik) | Namespaces, workflow repositories, grants and tokens, as HCL. |
| [agentiik.github.io](https://github.com/agentiik/agentiik.github.io) | The site and the documentation. |

### Licensing

The server is AGPL-3.0-or-later; everything a third party has to embed (the schemas, the
SDK, the bricks, the tokens, the deployment templates) is Apache-2.0. A brick is not a
derivative work of the engine. [LICENSING.md](https://github.com/agentiik/.github/blob/main/LICENSING.md)
sets out the split and the reasoning.
