---
type: cli
actors:
- operator
references:
- kind: code
  role: context
  target: wp-document-revisions.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-validate-cli-command.php
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-cli-command.php
---

# WP-CLI commands

The `wp document-revisions` commands an operator runs from a shell to check and repair documents and to extract the text of existing files.
