---
appliesTo:
- type: capability
  id: summarize-revision
- type: entity
  id: revision
  facts:
  - Summary
references:
- kind: code
  role: implementation
  target: src/admin/wp-document-revisions-ai-prefill.js
---

# An AI suggestion changes nothing until the person editing saves it

The suggestion only fills an empty revision summary; the person edits, keeps or dismisses it, and it becomes a revision summary only when they press Update.
