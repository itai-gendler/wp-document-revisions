---
availability:
- place: web::signed-in
- place: wp-cli
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extractor-scheduler.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extractor-registry.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-cli-command.php
- kind: doc
  role: intent
  target: docs/cookbook/text-extraction-and-ai-summaries.md
---

# Extract document text

The Product takes the plain text out of each new document file in PDF, DOCX or ODT format, shortly after it is uploaded, and keeps it with the revision for searching, AI summaries and other uses. An operator fills in the text of files uploaded before. Documents set to skip text extraction are left out.
