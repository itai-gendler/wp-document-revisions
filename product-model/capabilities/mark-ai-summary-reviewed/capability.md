---
availability:
- place: web::signed-in
domain: documents
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary-rest.php#WP_Document_Revisions_AI_Summary_REST.can_review_summary
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions-ai-prefill.js
- kind: doc
  role: intent
  target: docs/cookbook/text-extraction-and-ai-summaries.md
---

# Mark AI summary reviewed

A person who may edit a document marks the AI summary offered in its revision summary as reviewed, recording that someone checked it.
