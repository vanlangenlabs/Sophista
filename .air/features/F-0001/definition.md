# Feature Definition: answer questions from knowledge

## Proposal source

Feature proposal F-0001, `.air/features/F-0001/proposal.md`, and the approved
Sophista Concept, `.air/concept.md` (SHA-256
`7501e84bca985c167723f1a9e13bb0cf94589110978b951506b687b7b5701081`).

## Problem and user outcome

People asking questions through a Sophista client need answers grounded in
relevant Markdown knowledge, with source information they can use to verify
where the answer came from.

## In scope

- Answer a user's question using relevant Markdown knowledge available to the
  selected Sophista profile.
- Cite the knowledge used in the answer. Show the current content node and its
  parent nodes so the source location can be traced through the document.
- If a cited content node has no name, identify it with a one-sentence
  description based on its context.
- When no relevant organizational source is found, allow an answer from the
  language model's general knowledge, while clearly disclosing that it is not
  based on found organizational knowledge.

## Out of scope

- Importing or interpreting source materials; external applications perform
  those responsibilities.
- Defining or implementing knowledge-management and embedding lifecycle
  behavior; these are product capabilities in the approved Concept, not part of
  this question-answering feature.
- User management, which is provided by another application.
- Technical design or implementation choices.

## Acceptance criteria

- Given a question and relevant Markdown knowledge available to the selected
  profile, Sophista returns an answer based on relevant knowledge and includes
  source information for the cited content.
- Each cited location identifies the current content node and its parent nodes.
- If a cited content node has no name, its citation includes a one-sentence
  description based on context.
- Given that no relevant organizational source is found, Sophista may return an
  answer from general model knowledge, and the response clearly discloses that
  the answer is not based on found organizational knowledge.
- A user can use the returned citation to trace the answer's supporting
  information to its location in the source document.

## Dependencies and constraints

- The approved Concept requires traceable citations and permits general
  model-knowledge fallback only when clearly disclosed.
- Markdown knowledge is made available to profiles through the knowledge
  capabilities described by the approved Concept. Source importing and
  interpretation remain the responsibility of external applications.
- Keep the Definition at the product-behavior level; defer technical choices to
  Design.

## Open questions

- Should a source citation also include a URI, or are the node and parent
  locations and contextual descriptions sufficient? URI support was raised as
  a possibility but has not been confirmed.

## Decisions and evidence

- The owner identified answering questions from Markdown knowledge with
  verifiable source information as a desired user outcome.
- The owner confirmed that general model knowledge may be used when no relevant
  source is found if this is clearly disclosed.
- The owner specified that a source location should traverse from the current
  node through its parent nodes. For an unnamed content node, the citation
  should use a one-sentence description based on context.
- The owner clarified that source citation is a foundational element of
  Sophista, not a feature by itself.
- The owner requested proceeding to the next phase. This authorizes preparing
  this Definition draft; it is not approval of the feature or this Definition.
