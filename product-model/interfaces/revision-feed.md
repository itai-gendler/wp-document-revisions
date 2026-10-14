---
type: api
actors:
- subscriber
- contributor
- author
- editor
- administrator
entryPoints:
- api: /documents/<document-slug>/feed/?key=<secret-feed-key>
references:
- kind: code
  role: implementation
  target: includes/revision-feed.php
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.revision_feed_auth
---

# Revision feed

The RSS feed of each document's revision log, which a person adds to their feed reader with their secret feed key so the reader opens it as them.
