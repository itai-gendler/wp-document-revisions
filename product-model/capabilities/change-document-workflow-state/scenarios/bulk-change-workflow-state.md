---
kind: alternative
routes:
  web: Web
steps:
- text: The Editor selects several documents in All Documents and sets their workflow state with Bulk Edit
  kind: actor
  actor: editor
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
  - entity: workflow-state
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::documents-list
- text: The Product puts each document in that workflow state and sends one email per document when workflow state emails are on
  kind: product
  actor: editor
  entities:
  - entity: document
    effect: changes
    facts:
    - Workflow state
    - Last modified
  - entity: document-settings
    effect: reads
    facts:
    - Email notifications
    - Notify on workflow state change
    - Notification recipients
  - entity: account
    effect: reads
    facts:
    - Email
  - entity: workflow-state
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::documents-list
---

# Change the workflow state of several documents

## Trigger

A batch of documents is approved together.

## Outcome

Every selected document is in the new workflow state.
