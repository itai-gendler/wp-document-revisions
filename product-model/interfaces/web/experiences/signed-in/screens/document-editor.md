---
entities:
- entity: document
  shows:
  - Title
  - Description
  - File
  - Owner
  - Workflow state
  - Visibility
  - Password
  - Slug
  - Permanent link
  - Publish date
  - Document image
  - Skip text extraction
  - Do not pre-fill
  - Last modified
  collects:
  - Title
  - Description
  - File
  - Owner
  - Workflow state
  - Visibility
  - Password
  - Slug
  - Publish date
  - Document image
  - Skip text extraction
  - Do not pre-fill
- entity: revision
  shows:
  - Number
  - File
  - Saved by
  - Saved at
  - Summary
  - AI summary
  - AI summary reviewed by
  collects:
  - Summary
- entity: document-lock
  shows:
  - Holder
- entity: workflow-state
  shows:
  - Name
- entity: account
  shows:
  - Display name
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions.js
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-opt-out.php#WP_Document_Revisions_Text_Extraction_Opt_Out.render_meta_box
---

# Document editor

Add New Document and Edit Document: one document with its file and Upload New Version, description, revision summary, revision log, workflow state, owner, publishing and visibility, document image, permalink and its text extraction and AI choices.
