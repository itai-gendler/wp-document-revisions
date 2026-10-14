---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: document
  verb: owns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# Author

A signed-in person who creates, uploads new versions of, publishes and deletes their own documents, and reads earlier revisions of the documents they may read.
