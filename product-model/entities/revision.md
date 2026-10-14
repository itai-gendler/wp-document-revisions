---
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.get_revisions
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extractor-cache.php
---

# Revision

One saved version of a document. A revision is kept each time a new file is checked in or the title or description changes, and it keeps the file the document had at that moment.

## Information kept

- **Number** — its place in the document's history, starting at 1
- **File** — the file this version holds, at its own address ending in -revision- and its number
- **Saved by** — the person who saved it
- **Saved at** — when it was saved
- **Summary** — the revision summary written when it was saved
- **Extracted text** — the plain text taken from its file, for searching, summaries and other uses
- **AI summary** — one to three sentences from a language model on what changed since the previous version, or on the whole file for a first version
- **AI summary reviewed by** — who marked the AI summary as reviewed, and when
