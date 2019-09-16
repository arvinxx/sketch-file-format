# Sketch File Format

> A JSON Schema for the Sketch file format.

## Overview

This is a manually maintained JSON Schema based on
[Draft 7](https://json-schema.org/draft-07/json-schema-release-notes.html) of
the JSON Schema specification. The objective is to craft a schema that describes
as closely as possible the shape of Sketch JSON files on disk.

In order to aid maintainability the schema is split up into multiple reusable
sub-schema in separate files. Yaml is used to improve readability of the
schemas, introduce the possibility of leaving comments etc. Final JSON schema
files are then produced in a build step.

> The schema files in this repo are hand-editable but tooling can be used to
> improve the developer experience. Node, yarn and VS Code are required to make
> the most of the tooling in this repo, although this sort of developer
> environment is purely optional.

## Scripts

| Script                | Description                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------- |
| yarn build            | Builds distributable schema into the `dist` folder                                                 |
| yarn validate         | Checks the schema for correctness against the Draft 7 meta-schema                                  |
| yarn watch            | Runs `yarn validate` whenever a YAML file changes in the `schema/` folder                          |
| yarn integration-test | Uses the built schemas to validate real Sketch files, false negatives are treated as test failures |
| yarn test             | Unit tests (not implemented yet)                                                                   |
| yarn format-check     | Checks the repo with Prettier                                                                      |
