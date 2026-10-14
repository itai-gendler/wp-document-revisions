---
entities:
- entity: document
  shows:
  - Title
  - Owner
  - Workflow state
  - File
  - Visibility
  - Last modified
  - Publish date
- entity: revision
  shows:
  - Number
- entity: document-lock
  shows:
  - Holder
- entity: workflow-state
  shows:
  - Name
  collects:
  - Name
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-list.php
---

# All Documents

The list of every document the person may see in the Documents menu, with its owner, workflow state, file, number of revisions and who is currently editing it, filtered by workflow state, owner or missing file.
