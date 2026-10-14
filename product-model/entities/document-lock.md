---
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.get_document_lock
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.take_document_lock
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# Document lock

The hold a person takes on a document by opening it to edit it, so that nobody else changes it meanwhile: the document is checked out to them.

## Information kept

- **Holder** — the person who has the document checked out
- **Last active** — when the holder's editor last told the site they are still on the document
