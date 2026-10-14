---
singleton: true
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.settings_fields
- kind: doc
  role: intent
  target: docs/notifications.md
---

# Document settings

The document settings the site keeps once, under Settings > Media, or for a whole network in its network settings.

## Information kept

- **Upload directory** — the folder document files are stored in; it may be outside the public web folder
- **Documents slug** — the first part of every document address, documents unless changed
- **Date in permalink** — whether document addresses include the year and month they were created
- **Email notifications** — whether emails are sent when documents change; off until turned on
- **Notification recipients** — email addresses told of every change, besides the document's owner
- **Notify on workflow state change** — whether a change of workflow state is emailed; on by default
- **Notify on new revision** — whether a newly saved revision is emailed; off by default
