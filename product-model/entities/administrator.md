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

# Administrator

A signed-in person who runs the site: everything an editor does, plus the document settings under Settings > Media and other people's feed keys.
