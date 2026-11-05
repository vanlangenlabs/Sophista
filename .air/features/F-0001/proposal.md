# Feature proposal: answer questions with traceable knowledge sources

## Proposal

Sophista answers a user's question using relevant Markdown knowledge and returns
source information the user can verify. The citation location should show the
current node and its parent nodes. When a content node has no name, its citation
should identify it with a one-sentence, context-based description. The owner
considers clear source citation fundamental to the product. A URI for a source
may also be useful, but whether URI support is required is not yet decided.

If no relevant source is found, the language model may answer from its general
knowledge, provided the result clearly identifies that it is not based on
found organizational knowledge.

## Evidence

The project owner described answering from Markdown knowledge with a verifiable
citation as the desired outcome and confirmed that general model knowledge may
be used when no relevant source is found if this is clearly disclosed. The owner
clarified that the citation location should include the current node and its
parents, and that unnamed content nodes should be described in one sentence
based on context. The owner raised URI support as a possibility, not a confirmed
requirement. Confirmation of F-0001's scope and URI support remains pending.

Source: owner responses in the task conversation on 2026-11-05.
