---
kind: alternative
routes:
  cli: WP-CLI
steps:
- text: The Operator runs the extract-text command with --missing
  kind: actor
  actor: operator
  entities: []
  contexts:
    cli:
      place: wp-cli
- text: The Product takes the text out of every revision file that has none and has not failed before, skipping documents that skip text extraction, and reports each one
  kind: product
  actor: operator
  entities:
  - entity: revision
    effect: changes
    facts:
    - Extracted text
  - entity: document
    effect: reads
    facts:
    - Skip text extraction
  contexts:
    cli:
      place: wp-cli
---

# Fill in the text of earlier files

## Trigger

A library existed before text extraction.

## Outcome

Older revisions have their text; --all, --id, --force and --dry-run choose other sets or preview the run.
