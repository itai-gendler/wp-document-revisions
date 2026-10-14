---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Delete Permanently for their document in the trash
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product deletes the document with all its revisions and the stored file of every version
  kind: product
  actor: author
  entities:
  - entity: document
    effect: removes
    from: Trashed
  - entity: revision
    effect: removes
    with: document
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Delete a document permanently

## Trigger

A trashed document is no longer needed.

## Outcome

Nothing of the document is left, including files kept outside the public web folder.

## Edge cases

- Files uploaded to the document but never saved as a version are deleted too.
