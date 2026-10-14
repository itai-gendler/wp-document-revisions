---
appliesTo:
- type: capability
  id: change-document-workflow-state
- type: capability
  id: upload-new-version
references:
- kind: doc
  role: intent
  target: docs/notifications.md
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-notifications.php
---

# Workflow state changes and new revisions are emailed to the recipient list and the owner, never to whoever made the change

When notifications are on, each recipient gets their own copy, duplicate and invalid addresses are dropped, and the person who made the change is never told of it.
