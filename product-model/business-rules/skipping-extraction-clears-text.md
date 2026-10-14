---
appliesTo:
- type: entity
  id: revision
  facts:
  - Extracted text
  - AI summary
- type: capability
  id: edit-document
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-opt-out.php#WP_Document_Revisions_Text_Extraction_Opt_Out.clear_cached_text_for_document
---

# Skipping text extraction clears a document's text and AI summaries

Once a document is set to skip text extraction, the text and AI summaries already kept for its revisions are removed and none are made until it is unset.
