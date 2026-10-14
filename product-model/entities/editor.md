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

# Editor

A signed-in person who manages everyone's documents: edits, publishes and deletes any of them, reads private ones, gives documents to another owner, overrides other people's locks and keeps the list of workflow states.
