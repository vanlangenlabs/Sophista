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
- next_action: Await owner answers to the focused Concept questions below; update only what those answers establish, then present the exact revised Concept for review and explicit approval. Do not begin feature intake before approval.

## Records
| ID | Type | Path | record_status | Current SHA-256 | Approved SHA-256 | Depends on | Tracker reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-0001 | README | `.air/README.md` | none | `97b1b7b15f0f9510074eadb22a23e173b0d2dc279eaa285a3d7cab4620b6291b` | none | none | none |
| R-0002 | Index | `.air/index.md` | none | unknown (self-referential) | none | none | none |
| R-0003 | Concept | `.air/concept.md` | draft | `aad858605aca1029dc6df6cbb6e4826a1de7a8886c159852ce8a62b7922754b7` | none | none | none |

## Features
| Feature ID | Definition record ID | feature_status | Active release ID or none | Prior status if blocked | Event reference |
| --- | --- | --- | --- | --- | --- |

## Releases
| Release ID | Scope record ID | Design record ID or none | release_status | Prior status if blocked | Event reference |
| --- | --- | --- | --- | --- | --- |

## Approval and change events
| Event ID | Kind: decision/change | Record/entity | Old/new SHA-256 | Decision or change classification | Actor | Timestamp | Evidence and rationale | Affected records/checks/events | Next state |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-0001 | change | R-0003 | none -> `ab8b892e13b68a5068c91792d4743e5d5eafad588bacc3bda048a88e4deb8224` | Initial Concept draft | Copilot | 2026-11-05T14:37:38Z | Drafted from the owner's Sophista specification in the task conversation; technical choices were kept out of the Concept and remain open for confirmation. | No prior records, checks or approvals affected. | Await explicit human review/approval of this exact digest. |
| A-0002 | change | R-0003 | `ab8b892e13b68a5068c91792d4743e5d5eafad588bacc3bda048a88e4deb8224` -> `aad858605aca1029dc6df6cbb6e4826a1de7a8886c159852ce8a62b7922754b7` | Material Concept revision | Copilot | 2026-11-05T14:48:36Z | Incorporated the owner's clarification that OpenWebUI owns user accounts/roles and that the profile/RAG/routing/streaming architecture is foundational. Explained success measures and retained unresolved product questions without inventing answers. | Prior pending approval request I-0002 targets the old digest and is no longer current; no approval had been recorded. | Await owner answers; revise if needed, then self-review and request approval for the exact current digest. |

## Verification evidence
| Feature/release | Check | Result | Evidence path/reference | Digest | Current/stale and reason |
| --- | --- | --- | --- | --- | --- |

## Pending interaction
| ID | Type | State | Target record/digest | Request and allowed outcomes | Response/evidence | Prior node/call stack | Next action or blocker |
| --- | --- | --- | --- | --- | --- | --- | --- |
| I-0001 | Question | resolved | Concept / no record drafted | What do you want this project to do, or what problem should it solve? Who is it for, and what outcome should it create? What boundaries or non-goals should guide it? How would you recognize success, and what decisions or evidence should support that direction? A narrative answer is fine; unanswered points will remain open. | Owner provided the Sophista RAG Proxy & Profile Middleware specification in the task conversation on 2026-11-05. | Project.start -> restore -> conceptNeeded -> Concept.start -> concept | Draft `.air/concept.md`; retain unresolved details for review. |
| I-0002 | Approval | working | R-0003 `.air/concept.md`, old SHA-256 `ab8b892e13b68a5068c91792d4743e5d5eafad588bacc3bda048a88e4deb8224` | The owner reviewed the prior draft and gave clarification/questions; no approval was given. This request is stale after the material revision. | Owner clarified that OpenWebUI owns user accounts/roles, asked what success measures mean, requested guided boundary questions, and stated the described architecture is central. | Project.start -> restore -> conceptNeeded -> Concept.start -> conceptApproval | Replaced by I-0003 for the revised draft. |
| I-0003 | Question | awaiting-input | R-0003 `.air/concept.md`, SHA-256 `aad858605aca1029dc6df6cbb6e4826a1de7a8886c159852ce8a62b7922754b7` | Please answer what you can: (1) Are HR and technical profiles examples or the intended initial knowledge domains? (2) If retrieval finds no relevant source, should Sophista answer only from available sources or may it use general model knowledge; should it show its sources? (3) Is OpenWebUI's user/role handling sufficient, or must Sophista receive identity/access context to filter knowledge? (4) Which outcome matters most to assess first—relevance of retrieved knowledge, answers grounded in that knowledge, response time, or something else—and what would convince you? No numeric targets are needed yet. | Awaiting owner response. | Project.start -> restore -> conceptNeeded -> Concept.start -> concept | Incorporate only answered points; retain gaps visibly. Then present the exact current Concept for review and explicit approval; do not begin feature intake before approval. |
