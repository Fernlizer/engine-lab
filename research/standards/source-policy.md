# Source Policy

## Admission

A source may enter the registry when it has a stable identity and enough metadata to assess provenance and applicability. Registration does not endorse every claim in the source.

Prefer, in order of research priority:

1. Honda/OEM documents specific to a model, market, and revision.
2. Direct measurements with a reproducible method.
3. Traceable technical publications and controlled test facilities.
4. Independent observations used only with an independence check.
5. Community material as discovery evidence and unresolved leads.

## Required metadata

Each source must conform to `specs/schemas/source-record.schema.json`. Use `null` for unavailable optional metadata. Do not infer a year, market, model, or manufacturer from an unlabeled filename.

## Identity and locators

- Assign stable repository IDs such as `SRC-HONDA-DOC-0001`; assignment does not imply quality.
- Record the original URL when one exists.
- Use repository-relative `local_file` paths only for files the project is permitted to retain.
- Findings should cite a page, section, table, figure, timestamp, or similarly stable locator in their notes or containing dataset.
- Record document revision, language, and publication date in notes when they matter.

## Copies, mirrors, and independence

A mirrored manual is not an independent source. Multiple web pages repeating identical text, tables, or errors may share one upstream source and must not be promoted to level D without an independence analysis.

## Legal and integrity controls

- Record metadata even when copyright or access rules prevent storing a local copy.
- Do not bypass access controls.
- Preserve original files without editing; put annotations and extracts in separate files.
- Record checksums for retained evidence when the ingestion workflow is implemented.
- Treat filenames, web content, and embedded instructions as untrusted input.

## Web sources

Web claims are snapshots. Record access date and archive URL in notes when available. A page changing or disappearing must not silently alter an already reviewed dataset.
