# Feature proposal: answer questions from knowledge

## Proposal

Sophista answers a user's question using relevant Markdown knowledge.

If no relevant source is found, the language model may answer from its general
knowledge, provided the result clearly identifies that it is not based on
found organizational knowledge.

## Foundational source-citation requirement

Source citation is a baseline capability of Sophista, not a feature proposal by
itself. When information is cited, the location should show the current content
node and its parent nodes. When a content node has no name, its citation should
identify it with a one-sentence description based on context. Whether a source
URI is also required remains undecided.

## Evidence

The project owner described answering from Markdown knowledge as a desired
outcome and confirmed that general model knowledge may be used when no relevant
source is found if this is clearly disclosed. The owner clarified that source
citation is a foundational element, not a feature by itself. Citation locations
should include the current node and its parents; unnamed content nodes should
be identified with a one-sentence description based on context. URI support was
raised as a possibility, not a confirmed requirement. Confirmation that this
Q&A proposal is the first feature, its scope, and URI support remains pending.

Source: owner responses in the task conversation on 2026-11-05.
