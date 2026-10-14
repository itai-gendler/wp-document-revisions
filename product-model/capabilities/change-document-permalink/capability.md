---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-rewrites.php#WP_Document_Revisions_Rewrites.update_post_slug_field
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-rewrites.php#WP_Document_Revisions_Rewrites.old_slug_redirect_post_id
---

# Change document permalink

A person edits the name in a document's permanent link from the document editor; the old address then leads to the new one for people who may see the document.
