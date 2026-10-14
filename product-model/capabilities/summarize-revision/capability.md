---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary-prefill.php
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions-ai-prefill.js
- kind: doc
  role: intent
  target: docs/cookbook/text-extraction-and-ai-summaries.md
---

# Summarize revision

Once a new file's text is extracted, the Product asks the language model the site has connected for one to three sentences on what changed since the previous version, or on the whole file for a first version, and keeps it with the revision. When the document is opened, the summary is offered in the empty revision summary as an AI suggestion to edit before saving. Private and password-protected documents get no summary.
