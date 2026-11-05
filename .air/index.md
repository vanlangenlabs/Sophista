# AIRFlow project index

## Workflow source
- entry: https://raw.githubusercontent.com/vanlangenlabs/vanlangenlabs-site/52b9308697b5c8ac4baa3660071490be7e5e7aa8/docs/airflow/airflow.md

| Source path | Role | Ref (commit/tag) | SHA-256 |
| --- | --- | --- | --- |
| `docs/airflow/airflow.md` | Entry point and shared instructions | `52b9308697b5c8ac4baa3660071490be7e5e7aa8` | `e8efa3269c8be1320f75aac44fd5fc78b6ddce5f5e5c268f263e08cedc93714a` |
| `docs/airflow/flows/project.mmd` | Project orchestration flow | `52b9308697b5c8ac4baa3660071490be7e5e7aa8` | `c2df447df194476e55ab928c30f4de7053e122ce5dac9738bccb01fd43e9d0ea` |
| `docs/airflow/flows/concept.mmd` | Concept phase flow | `52b9308697b5c8ac4baa3660071490be7e5e7aa8` | `6fa64bc1aceafaa158ec036b4e58c07792cad863fa3d86100d03134de7b0531f` |

## Tracker integration
- provider: github
- project_or_board: none

## Current execution
- status: waiting-human
- phase: Concept
- node_id: concept
- call_stack: Project.start -> Project.restore -> Project.conceptNeeded -> Concept.start -> Concept.concept
- call_arguments: none
- pending_targets: none
- feature_id: none
- release_id: none
- next_action: Await project-owner answers to the pending Concept questions. Do not draft `.air/concept.md` until answered.

## Records
| ID | Type | Path | record_status | Current SHA-256 | Approved SHA-256 | Depends on | Tracker reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-0001 | README | `.air/README.md` | none | `97b1b7b15f0f9510074eadb22a23e173b0d2dc279eaa285a3d7cab4620b6291b` | none | none | none |
| R-0002 | Index | `.air/index.md` | none | unknown (self-referential) | none | none | none |

## Features
| Feature ID | Definition record ID | feature_status | Active release ID or none | Prior status if blocked | Event reference |
| --- | --- | --- | --- | --- | --- |

## Releases
| Release ID | Scope record ID | Design record ID or none | release_status | Prior status if blocked | Event reference |
| --- | --- | --- | --- | --- | --- |

## Approval and change events
| Event ID | Kind: decision/change | Record/entity | Old/new SHA-256 | Decision or change classification | Actor | Timestamp | Evidence and rationale | Affected records/checks/events | Next state |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## Verification evidence
| Feature/release | Check | Result | Evidence path/reference | Digest | Current/stale and reason |
| --- | --- | --- | --- | --- | --- |

## Pending interaction
| ID | Type | State | Target record/digest | Request and allowed outcomes | Response/evidence | Prior node/call stack | Next action or blocker |
| --- | --- | --- | --- | --- | --- | --- | --- |
| I-0001 | Question | awaiting-input | Concept / no record drafted | What do you want this project to do, or what problem should it solve? Who is it for, and what outcome should it create? What boundaries or non-goals should guide it? How would you recognize success, and what decisions or evidence should support that direction? A narrative answer is fine; unanswered points will remain open. | Awaiting project-owner response | Project.start -> restore -> conceptNeeded -> Concept.start -> concept | Use the answers to draft `.air/concept.md`, keep unresolved questions visible, then request review and explicit approval; do not begin feature intake before approval. |
