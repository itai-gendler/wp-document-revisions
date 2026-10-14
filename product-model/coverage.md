---
scope: 'The WP Document Revisions plugin: documents, revisions, locking, workflow states, file delivery, front-end blocks and shortcodes, notifications, settings, text extraction, AI summaries, Validate Structure and the WP-CLI commands.'
method: Static inspection of source, tests and documentation at commit 8fe4d95f; nothing was run.
covered:
- description: Document post type, roles and capabilities, workflow state taxonomy, queries and permission filters
  paths:
  - includes/class-wp-document-revisions.php
  - includes/trait-wp-document-revisions-query.php
  - includes/trait-wp-document-revisions-revisions.php
- description: File upload, storage, serving, permalinks, rewrite rules and the revision feed
  paths:
  - includes/trait-wp-document-revisions-file-handler.php
  - includes/trait-wp-document-revisions-rewrites.php
  - includes/revision-feed.php
  - includes/template-functions.php
- description: Document edit screen, documents list, dashboard widget, profile feed key and Media settings
  paths:
  - includes/class-wp-document-revisions-admin.php
  - includes/trait-wp-document-revisions-admin-editor.php
  - includes/trait-wp-document-revisions-admin-list.php
  - includes/trait-wp-document-revisions-admin-settings.php
  - src/admin/wp-document-revisions.js
  - css/
- description: 'Front-end shortcodes, blocks and widget: document list, library, revisions, preview and latest documents'
  paths:
  - includes/class-wp-document-revisions-front-end.php
  - includes/class-wp-document-revisions-document-library.php
  - includes/class-wp-document-revisions-recently-revised-widget.php
  - src/blocks/
- description: Email notifications
  paths:
  - includes/class-wp-document-revisions-notifications.php
- description: Text extraction, opt-outs, AI revision summaries, pre-fill and their REST routes
  paths:
  - includes/interface-wp-document-revisions-text-extractor.php
  - includes/class-wp-document-revisions-text-extraction-exception.php
  - includes/class-wp-document-revisions-text-extractor-registry.php
  - includes/class-wp-document-revisions-text-extractor-cache.php
  - includes/class-wp-document-revisions-text-extractor-scheduler.php
  - includes/class-wp-document-revisions-text-extraction-opt-out.php
  - includes/class-wp-document-revisions-pdf-text-extractor.php
  - includes/class-wp-document-revisions-docx-text-extractor.php
  - includes/class-wp-document-revisions-text-diff.php
  - includes/class-wp-document-revisions-unified-diff-renderer.php
  - includes/class-wp-document-revisions-ai-summary.php
  - includes/class-wp-document-revisions-ai-summary-rest.php
  - includes/class-wp-document-revisions-ai-summary-prefill.php
  - src/admin/wp-document-revisions-ai-prefill.js
- description: Validate Structure screen and the WP-CLI commands
  paths:
  - includes/class-wp-document-revisions-validate-structure.php
  - includes/class-wp-document-revisions-validate-cli-command.php
  - includes/class-wp-document-revisions-text-extraction-cli-command.php
  - src/admin/wp-document-revisions-validate.js
exclusions:
- description: Tests, CI, release, build and development tooling
  paths:
  - tests/
  - .github/
  - .devcontainer/
  - .claude/
  - script/
  - vendor-bin/
  - .distignore
  - .gitattributes
  - .gitignore
  - .npmrc
  - .prettierignore
  - .prettierrc.json
  - .wp-env.json
  - babel.config.json
  - composer.json
  - composer.lock
  - docker-compose.yml
  - eslint.config.cjs
  - jsconfig.json
  - package.json
  - package-lock.json
  - phpcs.ruleset.xml
  - phpstan.neon.dist
  - phpunit9.xml
  - playwright.config.mjs
  - renovate.json
  - scoper.inc.php
  - CLAUDE.md
- description: Plugin bootstrap, translations, images, plugin directory assets, documentation and license
  paths:
  - wp-document-revisions.php
  - languages/
  - img/
  - .wordpress-org/
  - docs/
  - README.md
  - readme.txt
  - LICENSE
unmapped:
- description: Block editor document editing (opt-in by code) and the REST exposure of documents it relies on
  paths:
  - src/editor-document-upload/
  - includes/class-wp-document-revisions-manage-rest.php
- description: Uninstall clean-up of options, feed keys and capabilities
  paths:
  - uninstall.php
limitations: []
---

# Coverage
