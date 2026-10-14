---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs the validate command
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product lists the problems of every document as a table, CSV, JSON or a count
  kind: product
  actor: operator
  entities:
  - entity: document
    effect: reads
    facts:
    - Title
    - File
    - Permanent link
  contexts:
    cli:
      place: wp-cli
---

# Check every document from the command line

## Trigger

A large library is checked from a scheduled job.

## Outcome

The Operator sees every problem, whoever owns the document.
