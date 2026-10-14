---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
---

# Subscriber

A signed-in member of the site who may read documents but not create them or read their earlier revisions: the least privileged signed-in role, standing for any signed-in person when they read published documents, follow a document feed or keep their own feed key.
