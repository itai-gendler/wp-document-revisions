---
appliesTo:
- type: entity
  id: revision
  facts:
  - AI summary
- type: capability
  id: summarize-revision
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary.php#WP_Document_Revisions_AI_Summary.is_allowed_for_document
---

# Private and password-protected documents get no AI summary

Nothing of a private or password-protected document is sent to a language model, and nothing at all of a document set to skip text extraction.
