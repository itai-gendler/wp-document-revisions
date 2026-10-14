---
kind: primary
routes:
  feed: Revision feed
steps:
- text: The Contributor adds the feed address of a document, with their secret feed key, to their feed reader
  kind: actor
  actor: contributor
  entities:
  - entity: account
    effect: reads
    facts:
    - Secret feed key
  - entity: document
    effect: reads
    facts:
    - Title
  contexts:
    feed:
      place: revision-feed
- text: The Product returns the document's revisions with who saved each, when and its summary
  kind: product
  actor: contributor
  entities:
  - entity: revision
    effect: reads
    facts:
    - Number
    - Saved by
    - Saved at
    - Summary
  - entity: document
    effect: reads
    facts: []
  contexts:
    feed:
      place: revision-feed
---

# Follow a revision log

## Trigger

The Contributor wants to hear of new versions without opening the site.

## Outcome

Each new revision appears in the feed reader, linked to its file.
