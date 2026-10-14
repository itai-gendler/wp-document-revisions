---
kind: alternative
routes:
  web: Web
steps:
- text: The Author picks a workflow state, an owner or Missing file and filters the list
  kind: actor
  actor: author
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product lists only the documents that match
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
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Filter documents by workflow state, owner or missing file

## Trigger

The Author looks for the documents under review, the documents of one owner, or documents that have lost their file.

## Outcome

Only the matching documents are listed; sorting by number of revisions or by file type also works.
