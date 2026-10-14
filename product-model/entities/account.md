---
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-admin-settings.php#WP_Document_Revisions_Admin_Settings.rss_key_display
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.validate_feed_key
---

# Account

A person's user account on the site, as WP Document Revisions uses it: who they are, where its emails reach them and the key their document feeds open with.

## Information kept

- **Display name** — the name shown for them as owner, as the person who saved a revision and as the holder of a lock
- **Email** — where notifications and lock override emails reach them
- **Secret feed key** — a 32-character key that opens document feeds as them in a feed reader; created the first time it is needed
