---
appliesTo:
- type: entity
  id: revision
  facts:
  - Extracted text
- type: capability
  id: extract-document-text
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extractor-registry.php#WP_Document_Revisions_Text_Extractor_Registry.check_limits
---

# Files over 20 MB are not read for text

Text is taken only from files up to 20 MB, and a file that failed is not tried again until it is replaced.
