---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator enters a folder outside the public web folder as the upload directory and saves
  kind: actor
  actor: administrator
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Upload directory
  contexts:
    web:
      place: web::administration::media-settings
- text: The Product stores new document files there and warns that existing files may need to be moved
  kind: product
  actor: administrator
  entities:
  - entity: document-settings
    effect: changes
    facts:
    - Upload directory
  - entity: document
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::media-settings
---

# Move the document upload directory

## Trigger

The site wants document files out of reach of direct web requests.

## Outcome

New versions are stored in the new folder; files already uploaded stay where they were until moved.

## Decision points

### Is the folder usable?

Whether the folder exists and can be written to.

- It exists and is writable → only the warning about existing files is shown
- It does not exist, or is not writable → a warning says so as well
