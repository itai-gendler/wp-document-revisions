---
kind: validation
routes:
  feed: Revision feed
steps:
- text: The Subscriber opens the feed address of a document with a missing or out-of-date key
  kind: actor
  actor: subscriber
  entities:
  - entity: account
    effect: reads
    facts:
    - Secret feed key
  - entity: document
    effect: reads
    facts: []
  contexts:
    feed:
      place: revision-feed
- text: The Product refuses with Sorry, this is a private feed
  kind: product
  actor: subscriber
  entities: []
  contexts:
    feed:
      place: revision-feed
---

# A feed address without a valid key

## Trigger

A key was regenerated or never added.

## Outcome

No revision is shown.
