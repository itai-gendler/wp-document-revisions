---
availability:
- place: revision-feed
references:
- kind: code
  role: implementation
  target: includes/revision-feed.php
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.validate_feed_key
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-revisions.php#WP_Document_Revisions_Revisions.get_revision_query
---

# Follow revision feed

A person follows a document's revision log in their feed reader, through the document's feed address carrying their secret feed key.
