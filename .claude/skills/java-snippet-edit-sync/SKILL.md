---
name: java-snippet-edit-sync
description: Use when editing a snippet in src/main/java or README.md.
category: tooling
---

# Java snippet edits

Every change to a snippet in `src/main/java/{category}/` also goes into its matching code block in `README.md`, because README drives the website.

- Keep CRLF line endings. When rewriting files with Python, use `open(p, encoding='utf-8', newline='')`. Default text mode turns CRLF into LF, and git then warns that LF will be replaced by CRLF.
- Before replacing a README block, check that the old text is present and print the result. Rewrite the snippet and README together.
- Check `git diff --stat` before reporting, and confirm only the intended lines changed.
- Run the snippet's package tests, e.g. `./gradlew test --tests 'network.*'`.
- Follow AGENTS.md: stateless `public static` methods, `Locale.ENGLISH` for formatting, no third-party dependencies.
