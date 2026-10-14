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
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.network_settings_cb
---

# Network administrator

A person who runs a network of sites and sets, for all of them, where documents are stored and how their links are built.
