---
kind: primary
routes:
  web: Web
steps:
- text: The Network administrator enters an upload directory containing %site_id% and saves the network settings
  kind: actor
  actor: network-administrator
  entities:
  - entity: document-settings
    effect: reads
    facts:
    - Upload directory
    - Documents slug
    - Date in permalink
  contexts:
    web:
      place: web::administration::network-settings
- text: The Product stores the document settings for the whole network, each site's files in its own folder
  kind: product
  actor: network-administrator
  entities:
  - entity: document-settings
    effect: changes
    facts:
    - Upload directory
    - Documents slug
    - Date in permalink
  contexts:
    web:
      place: web::administration::network-settings
---

# Keep each site's files apart

## Trigger

A network runs one document repository per site.

## Outcome

Every site stores its documents in its own folder under the network's directory.
