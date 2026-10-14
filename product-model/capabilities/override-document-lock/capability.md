---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.override_lock
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.send_override_notice
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# Override document lock

An editor or administrator takes the lock on a document someone else has checked out. The previous holder is emailed that their lock was overridden and that any changes they made will be lost.
