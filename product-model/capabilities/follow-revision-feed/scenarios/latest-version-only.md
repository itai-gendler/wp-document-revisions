---
kind: alternative
routes:
  feed: Revision feed
steps:
- text: The Subscriber adds the feed address of a published document, with their secret feed key, to their feed reader
  kind: actor
  actor: subscriber
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
- text: The Product returns only the latest version of the document
  kind: product
  actor: subscriber
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - Last modified
  contexts:
    feed:
      place: revision-feed
---

# Follow a document without access to its revisions

## Trigger

A member without access to earlier versions follows a document.

## Outcome

The feed shows the current version only.
