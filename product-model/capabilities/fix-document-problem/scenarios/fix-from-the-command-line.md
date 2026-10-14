---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs the validate command with --fix
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product applies the fix of every problem that has one and reports what it did
  kind: product
  actor: operator
  entities:
  - entity: document
    effect: changes
    facts:
    - File
    - Permanent link
  contexts:
    cli:
      place: wp-cli
---

# Fix every problem from the command line

## Trigger

A library has many repairable problems.

## Outcome

The repairable problems are fixed; running the command again shows any problem a fix revealed.
