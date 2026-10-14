---
availability:
- place: web::public
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-front-end.php#WP_Document_Revisions_Front_End.wpdr_document_preview_display
- kind: doc
  role: intent
  target: docs/shortcodes.md
---

# Preview document

A person reads a document's current file inline on a site page holding the Document Preview block or shortcode, without downloading it first.
