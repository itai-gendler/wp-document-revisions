---
kind: primary
routes:
  web: Web
steps:
- text: The Subscriber chooses Generate New Key under Feed Privacy on their profile and saves
  kind: actor
  actor: subscriber
  entities:
  - entity: account
    effect: reads
    facts:
    - Secret feed key
  contexts:
    web:
      place: web::signed-in::profile
- text: The Product gives the Subscriber a new secret feed key
  kind: product
  actor: subscriber
  entities:
  - entity: account
    effect: changes
    facts:
    - Secret feed key
  contexts:
    web:
      place: web::signed-in::profile
---

# Generate a new feed key

## Trigger

A feed address with the key was shared by mistake.

## Outcome

Only feed addresses with the new key open the Subscriber's feeds.
