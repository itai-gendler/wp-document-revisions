---
availability:
- place: web::signed-in
- place: wp-cli
domain: validate-structure
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-validate-structure.php#WP_Document_Revisions_Validate_Structure.fix_problem
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-validate-cli-command.php
---

# Fix document problem

A person applies the automatic fix for a problem Validate Structure found: linking the document to its file, giving the file a hidden name, moving it into the document folder, deleting unused files or repairing the stored address. Problems with no fix are solved by uploading a new version or trashing the document.
