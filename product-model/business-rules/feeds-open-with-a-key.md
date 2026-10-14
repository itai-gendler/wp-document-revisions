---
appliesTo:
- type: entity
  id: account
  facts:
  - Secret feed key
- type: capability
  id: follow-revision-feed
references:
- kind: code
  role: implementation
  target: includes/trait-wp-document-revisions-file-handler.php#WP_Document_Revisions_File_Handler.validate_feed_key
---

# A revision feed opens only with a valid secret feed key

A document's feed is served as the person whose key it carries, and shows only what that person may read; without a valid key the feed is refused.
