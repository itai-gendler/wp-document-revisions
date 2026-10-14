---
appliesTo:
- type: entity
  id: document
  effect: changes
  facts:
  - Title
  - Description
  - Slug
  - Permanent link
  - Workflow state
  - Document image
  - Skip text extraction
  - Do not pre-fill
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: owns
    entity: author
- related:
  - verb: owns
    entity: contributor
  when:
  - state: Draft
- related:
  - verb: owns
    entity: contributor
  when:
  - state: Pending Review
- actors:
  - operator
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.save_document
---

# A document's details are changed by its owner, an editor or an administrator

Editors and administrators change any document; an author changes the documents they own; a contributor changes their own only while it is a draft or pending review. An operator repairs a stored address from the command line.
