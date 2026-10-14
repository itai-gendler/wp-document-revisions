---
entities:
- entity: document-settings
  shows:
  - Upload directory
  - Documents slug
  - Date in permalink
  collects:
  - Upload directory
  - Documents slug
  - Date in permalink
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.network_settings_cb
---

# Network settings

The Document Settings section of a network's settings: the upload directory, slug and date in permalink for every site of the network.
