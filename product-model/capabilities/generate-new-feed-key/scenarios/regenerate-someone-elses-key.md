---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator chooses Generate New Key on another person's profile and saves
  kind: actor
  actor: administrator
  entities:
  - entity: account
    effect: reads
    facts:
    - Secret feed key
  contexts:
    web:
      place: web::signed-in::profile
- text: The Product gives that person a new secret feed key
  kind: product
  actor: administrator
  entities:
  - entity: account
    effect: changes
    facts:
    - Secret feed key
  contexts:
    web:
      place: web::signed-in::profile
---

# Regenerate another person's key

## Trigger

A member's feed address leaked.

## Outcome

That person's old feed addresses stop working.
