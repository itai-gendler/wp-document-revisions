---
kind: primary
routes:
  web: Web
steps:
- text: The Author picks Under Review as the workflow state and presses Update
  kind: actor
  actor: author
  entities:
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  - entity: document
    effect: reads
    facts:
    - Workflow state
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product puts the document in that workflow state
  kind: product
  actor: author
  entities:
  - entity: document
    effect: changes
    facts:
    - Workflow state
    - Last modified
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::document-editor
- text: The Product emails the notification recipients and the document owner, leaving out the Author, that the document moved from its old workflow state to the new one
  kind: product
  actor: author
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Email notifications
    - Notify on workflow state change
    - Notification recipients
  - entity: document
    effect: reads
    facts:
    - Title
    - Owner
    - Permanent link
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  - entity: account
    effect: reads
    facts:
    - Email
    - Display name
  contexts:
    web:
      place: web::signed-in::document-editor
---

# Move a document to Under Review

## Trigger

The Author is ready for the document to be reviewed.

## Outcome

The document shows Under Review in All Documents and in libraries that show the workflow state, and the reviewers on the recipient list hear about it.

## Decision points

### Is the change emailed?

Whether the site emails workflow state changes.

- Email notifications and Notify on workflow state change are both on → each recipient gets their own copy with the old and new state and a link, the Author excluded
- Either is off → no email is sent
