---
appliesTo:
- type: entity
  id: revision
  effect: changes
  facts:
  - Extracted text
  - AI summary
permits:
- unattended: true
- actors:
  - operator
  - editor
  - administrator
- related:
  - verb: keeps
    entity: document
  - verb: owns
    entity: author
- related:
  - verb: keeps
    entity: document
  - verb: owns
    entity: contributor
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-text-extraction-opt-out.php#WP_Document_Revisions_Text_Extraction_Opt_Out.save
---

# A revision's text and AI summary are written by the Product and cleared by people who may edit the document

The Product writes them in the background, and an operator from the command line; setting a document to skip text extraction clears them, which needs the permission to edit that document.
