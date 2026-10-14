---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Secret feed key
permits:
- actors:
  - administrator
- related:
  - verb: signs in with
    entity: subscriber
- related:
  - verb: signs in with
    entity: contributor
- related:
  - verb: signs in with
    entity: author
- related:
  - verb: signs in with
    entity: editor
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.profile_update_cb
---

# A secret feed key is replaced by the person it belongs to or an administrator

Each person generates a new key on their own profile; an administrator may do so on anyone's.
