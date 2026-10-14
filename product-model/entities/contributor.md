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

# Contributor

A signed-in person who creates documents and edits their own until they are published, submitting them for review rather than publishing; reads earlier revisions of the documents they may read.
