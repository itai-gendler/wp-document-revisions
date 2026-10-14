---
appliesTo:
- type: entity
  id: document-settings
  effect: changes
permits:
- actors:
  - administrator
  - network-administrator
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.network_upload_location_save
---

# Document settings are changed only by administrators or, for a network, its administrators

The settings under Settings > Media need the permission to manage the site's options; the network settings need the permission to manage the network's options.
