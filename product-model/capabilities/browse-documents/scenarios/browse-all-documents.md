---
kind: primary
routes:
  web: Web
steps:
- text: The Author opens All Documents in the Documents menu
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product lists the documents the Author may see with owner, workflow state, file type and size, number of revisions and who is currently editing each
  kind: product
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Owner
    - Workflow state
    - File
    - Visibility
    - Last modified
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  - entity: revision
    effect: reads
    facts:
    - Number
  - entity: document-lock
    effect: reads
    facts:
    - Holder
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Browse all documents

## Trigger

The Author wants an overview of the team's documents.

## Outcome

The Author sees every document they may see, including who has each one checked out; private documents of other people are left out unless their role reads private documents.

## Edge cases

- A document whose file is linked but gone from storage shows Missing in its File column.
