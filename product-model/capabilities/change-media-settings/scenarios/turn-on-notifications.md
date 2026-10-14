---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator turns on email notifications, lists the reviewers' addresses, chooses the events and saves
  kind: actor
  actor: administrator
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Email notifications
    - Notification recipients
    - Notify on workflow state change
    - Notify on new revision
  contexts:
    web:
      place: web::administration::media-settings
- text: The Product saves the notification settings, keeping only valid addresses, once each
  kind: product
  actor: administrator
  entities:
  - entity: document-settings
    effect: changes
    facts:
    - Email notifications
    - Notification recipients
    - Notify on workflow state change
    - Notify on new revision
  contexts:
    web:
      place: web::administration::media-settings
---

# Turn on document notifications

## Trigger

Reviewers should hear when a document moves through the workflow.

## Outcome

From the next change on, the listed people and each document's owner are emailed, never about their own changes.
