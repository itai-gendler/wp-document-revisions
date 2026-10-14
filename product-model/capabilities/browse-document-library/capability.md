---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-document-library.php#WP_Document_Revisions_Document_Library.render
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-front-end.php#WP_Document_Revisions_Front_End.documents_shortcode
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-recently-revised-widget.php
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-query.php#WP_Document_Revisions_Query.can_list_document
- kind: doc
  role: intent
  target: docs/shortcodes.md
---

# Browse document library

A person browses documents on the site's own pages: the Document Library as a list, table or grid with the details the page chose, the Document List, the Latest Documents block or widget, and the documents archive. Each shows only the documents the person may see.
