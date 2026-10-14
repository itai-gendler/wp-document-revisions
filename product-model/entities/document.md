---
domain: documents
relations:
- entity: revision
  verb: keeps
  cardinality: one-to-many
- entity: document-lock
  verb: holds
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.register_cpt
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php
- kind: doc
  role: context
  target: docs/data-structure.md
- kind: doc
  role: intent
  target: docs/features.md
---

# Document

A file the team keeps and works on, with one permanent link, a description for readers and the full history of its versions.

## Information kept

- **Title** — the document's name
- **Description** — a short summary for readers, shown in document lists
- **File** — the file of its current version, served at its permanent link: its type and size
- **Owner** — the person who owns it: whoever created it unless an editor gives it to someone else
- **Workflow state** — the workflow state it is in, or none
- **Visibility** — Public, Password protected or Private; new documents are Private
- **Password** — what a visitor enters to download it while it is password protected
- **Slug** — the name in its permanent link
- **Permanent link** — the address that always serves its current file: the documents slug, the year and month unless the site leaves them out, the slug and the file's extension
- **Publish date** — when it was or will be published
- **Document image** — an image shown with it in document lists
- **Skip text extraction** — whether text is no longer taken from its files
- **Do not pre-fill** — whether AI suggestions stay out of its revision summary
- **Last modified** — when it last changed

## States

### Draft

Being prepared and not yet published; only people who may edit it reach it.

### Pending Review

Submitted by its contributor and waiting for someone who may publish it.

### Scheduled

Set to be published at its publish date.

### Published

Live at its permanent link for the people its visibility allows.

### Trashed

In the trash, off the site, and restorable until it is deleted permanently.
