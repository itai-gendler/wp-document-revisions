---
type: web
actors:
- visitor
- subscriber
- contributor
- author
- editor
- administrator
- network-administrator
entryPoints:
- web: /documents/<document-slug>.<extension>
- web: /documents/
- web: /wp-admin/edit.php?post_type=document
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-admin.php
---

# WP Document Revisions website

The WordPress site the plugin runs on: the documents' permanent links and the pages that list, preview and show the history of documents, and the WordPress admin where people sign in to manage documents, workflow states, their profile and the document settings.
