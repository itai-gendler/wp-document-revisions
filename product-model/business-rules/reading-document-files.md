---
appliesTo:
- type: entity
  id: document
  effect: reads
  facts:
  - File
permits:
- actors:
  - visitor
  - subscriber
  - contributor
  - author
  when:
  - state: Published
  - fact: Visibility
    is-not: Private
- actors:
  - editor
  - administrator
  - operator
- related:
  - verb: owns
    entity: author
- related:
  - verb: owns
    entity: contributor
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.serve_document_auth
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
---

# A document's file is read by everyone once it is published and not private, and otherwise only by its owner, editors and administrators

A published, public or password-protected document is served to anyone, visitors included, a password-protected one after its password is entered. A private document is served to its owner and to editors and administrators, who may read private documents. Drafts, pending, scheduled and trashed documents are served only to people who may edit them. An operator's commands read every document.
