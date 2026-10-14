---
entities:
- entity: document
  shows:
  - Title
  - Description
  - File
  - Document image
  - Workflow state
  - Owner
  - Last modified
- entity: workflow-state
  shows:
  - Name
- entity: revision
  shows:
  - Number
  - Saved by
  - Saved at
  - Summary
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-front-end.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-document-library.php
- kind: doc
  role: intent
  target: docs/shortcodes.md
---

# Site page

A post or page of the site holding one of the document blocks, or its shortcode or widget: Document Library, Document List, Latest Documents, Document Revisions or Document Preview.
