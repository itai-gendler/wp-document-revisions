---
availability:
- place: web::signed-in
- place: web::public
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.revision_metabox
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-front-end.php#WP_Document_Revisions_Front_End.revisions_shortcode
- kind: doc
  role: intent
  target: docs/shortcodes.md
---

# View revision history

A person reads a document's revision log: when each revision was saved, by whom and its summary, newest first, in the document editor or in a Document Revisions block on a site page.
