---
availability:
- place: web::signed-in
- place: wp-cli
domain: validate-structure
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-validate-structure.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-validate-cli-command.php
---

# Validate document structure

A person checks documents for problems between a document, its file and its permanent link: no file, a file that is missing or unreadable, a file not linked, a file not under a hidden name or outside the document folder, extra unused files, and a stored address that does not match the permanent link. In the web, it covers the documents the person may edit; from the command line, every document.
