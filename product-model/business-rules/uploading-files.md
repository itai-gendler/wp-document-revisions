---
appliesTo:
- type: entity
  id: document
  effect: changes
  facts:
  - File
permits:
- actors:
  - editor
  - administrator
- related:
  - verb: owns
    entity: author
- actors:
  - operator
references:
- kind: code
  role: implementation
  target: includes/class-wp-document-revisions.php#WP_Document_Revisions.add_caps
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-editor.php#WP_Document_Revisions_Admin_Editor.check_upload_files
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.filename_rewrite
---

# A document's file is replaced by its owning author, an editor or an administrator

A new version is uploaded, restored or relinked by people who may both edit the document and upload files: editors and administrators for any document, and authors for the documents they own. Contributors may not upload files. An operator relinks files from the command line.
