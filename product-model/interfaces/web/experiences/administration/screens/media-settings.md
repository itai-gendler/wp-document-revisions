---
entities:
- entity: document-settings
  shows:
  - Upload directory
  - Documents slug
  - Date in permalink
  - Email notifications
  - Notification recipients
  - Notify on workflow state change
  - Notify on new revision
  collects:
  - Upload directory
  - Documents slug
  - Date in permalink
  - Email notifications
  - Notification recipients
  - Notify on workflow state change
  - Notify on new revision
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.settings_fields
---

# Media settings

Settings > Media, with the Document Upload Directory, Document Slug, Document Date in Permalink and Document Notifications settings.
