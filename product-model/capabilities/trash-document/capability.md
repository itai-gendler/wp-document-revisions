---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# Trash document

A person moves a document to the trash from All Documents; it leaves the site with its revisions and files kept, and can be restored until it is deleted permanently.
