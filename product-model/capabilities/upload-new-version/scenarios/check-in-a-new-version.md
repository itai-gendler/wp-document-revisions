---
kind: primary
routes:
  web: Web
steps:
- text: The Author chooses Upload New Version on the checked-out document and selects the new file
  kind: actor
  actor: author
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product stores the file under a random name and asks the Author to press Update to save it
  kind: product
  actor: author
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Upload directory
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Author describes the change and presses Update
  kind: actor
  actor: author
  entities: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product makes the file the document's current version and records it as a new revision
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - File
    - Last modified
  - entity: revision
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
- text: The Product emails the notification recipients and the document owner, leaving out the Author, that a new revision was saved
  kind: product
  actor: author
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Email notifications
    - Notify on new revision
    - Notification recipients
  - entity: document
    effect: reads
    facts:
    - Title
    - Owner
    - Permanent link
  - entity: revision
    effect: reads
    facts:
    - Summary
  - entity: account
    effect: reads
    facts:
    - Email
    - Display name
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Check in a new version

## Trigger

The Author has finished changing the file.

## Outcome

The permanent link serves the new file, the revision log shows who checked it in, when and why, and anyone set to be told has an email with the summary and a link to the document.

## Decision points

### Are new-revision emails sent?

Whether the site emails a newly saved revision.

- Email notifications and Notify on new revision are both on → each recipient gets their own copy, the Author excluded
- Either is off → no email is sent

## Edge cases

- An address on the recipient list that is not a valid email address, or appears twice, is left out.
