---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Restore beside an earlier revision in the revision log and confirms
  kind: actor
  actor: author
  entities:
  - entity: revision
    as: earlier
    effect: reads
    facts:
    - Number
    - Saved at
    - Summary
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product copies that revision as the newest revision, making its file, title and description current again
  kind: product
  actor: author
  entities:
  - entity: revision
    as: earlier
    effect: reads
    facts:
    - File
  - entity: document
    effect: changes
    facts:
    - Title
    - Description
    - File
    - Last modified
  - entity: revision
    as: copy
    effect: creates
    facts:
    - Number
    - File
    - Saved by
    - Saved at
    - Summary
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Restore an earlier revision

## Trigger

A later version was a mistake.

## Outcome

The document is restored to that revision, "Document restored to revision from" its date shows, and every revision, including the one replaced, stays in the log.

## Edge cases

- The current revision, and revisions whose file is the current one, offer no Restore.
