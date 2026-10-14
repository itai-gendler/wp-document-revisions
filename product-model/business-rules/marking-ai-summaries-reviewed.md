---
appliesTo:
- type: entity
  id: revision
  effect: changes
  facts:
  - AI summary reviewed by
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: keeps
    entity: document
  - verb: owns
    entity: author
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions-ai-summary-rest.php#WP_Document_Revisions_AI_Summary_REST.can_review_summary
---

# An AI summary is marked reviewed by the owning author, an editor or an administrator

Marking a summary reviewed needs the permission to edit its document.
