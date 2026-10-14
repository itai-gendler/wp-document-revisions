---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.profile_update_cb
---

# Generate new feed key

A person replaces their secret feed key from their profile, so feed addresses carrying the old key stop working.
