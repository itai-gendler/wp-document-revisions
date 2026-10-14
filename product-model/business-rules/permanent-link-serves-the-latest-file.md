---
appliesTo:
- type: entity
  id: document
  facts:
  - Permanent link
- type: capability
  id: download-document
references:
- kind: doc
  role: intent
  target: docs/features.md
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-rewrites.php#WP_Document_Revisions_Rewrites.permalink
---

# A document's permanent link always serves its current file

However many versions are checked in or restored, the same address keeps working and serves the current one; each earlier version has an address of its own.
