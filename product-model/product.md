---
id: wp-document-revisions
summary: 'Document management and version control for WordPress: keep any file as a document with a permanent, access-controlled link, a full revision history with check-out locking, workflow states, owners, notifications and AI revision summaries.'
category: document-management
tags:
- document-management
- version-control
- collaboration
- wordpress-plugin
- revisions
authors:
- name: WP Document Revisions contributors
  url: https://github.com/wp-document-revisions/wp-document-revisions
license: GPL-3.0-or-later
languages:
- en
- da-DK
- de-DE
- es-ES
- fr-FR
- he-IL
- hu-HU
- id-ID
- it-IT
- ko-KR
- nb-NO
- nl-NL
- pl-PL
- pt-BR
- pt-PT
- ro-RO
- ru-RU
- sv-SE
- tr-TR
- zh-CN
- zh-TW
limitations:
- Who may read, edit, publish and delete documents follows the site's roles; the product adds document permissions to them and has no permission system of its own.
- 'Only one person edits a document at a time: whoever has it checked out holds a lock, and there is no simultaneous editing or merging of files.'
- 'The product tracks whole files, not changes inside them: finer history is left to the file format, such as tracked changes in a word processor.'
- 'Documents are not kept in folders: they are grouped by workflow state and by any categories the site adds to documents.'
- Email notifications are sent through the site's own mail setup, and AI summaries through the language model the site has connected.
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: intent
  target: readme.txt
  title: Plugin directory description
- kind: doc
  role: intent
  target: docs/features.md
- kind: doc
  role: intent
  target: docs/frequently-asked-questions.md
- kind: doc
  role: context
  target: docs/data-structure.md
---

# WP Document Revisions

WP Document Revisions turns a WordPress site into a document management system. A team uploads any kind of file as a document, gives it a title, a description, an owner and a workflow state such as Initial Draft, Under Review or Final, and checks in new versions as the work moves on. Every version becomes a revision with who saved it, when and a revision summary, and any earlier revision can be downloaded or restored. Whoever opens a document to edit it has it checked out, so nobody else changes it until they leave or an editor overrides the lock. Each document has one permanent link that always serves its latest file and is public, password protected or private, and the site can list documents on its pages, preview them, follow their history in a feed reader, email people when a document changes state or gains a version, and have a language model suggest a summary of what changed in each new version.

## Intent

"A powerful document management and version control plugin for WordPress. Collaborate on files, track every revision, search inside document contents, and auto-generate change summaries with AI." It is "three powerful tools in one": a document management system that tracks, stores and organizes files of any format, a collaboration tool for teams to draft, edit and refine documents, and secure file hosting to "publish and securely deliver files to teams, clients, or the public". It builds on what WordPress already does well (posts, attachments, revisions, taxonomies, authentication and permalinks) so that "with great power does not have to come great complexity".
