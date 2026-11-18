# @juanbenjumea/pi-todos

A Pi extension for project-scoped, file-backed todos. It provides an interactive `/todos` manager and a `todo` agent tool. Items live in `.pi/todos` as Markdown files with JSON front matter, so they remain inspectable and can be shared across sessions and other tools.

## Install

In Pi, install the package with:

```text
/package install npm:@juanbenjumea/pi-todos
```

For local development, load `./index.ts` as a Pi extension from this directory.

## Use

- Run `/todos` to browse and manage project todos.
- Ask the agent to check or update the project backlog; it can use the `todo` tool to list, create, inspect, update, append notes, claim, release, or close items.
- Todo IDs are displayed as `TODO-xxxxxxxx`.
- By default, storage is `<project>/.pi/todos`. Set `PI_TODO_PATH` to use another directory.

The extension uses per-item locks for writes and session claims to make concurrent work visible. It preserves the existing Pi todo file format. Closed-item cleanup behavior and settings are described in the extension source.

## Development

```sh
npm install
npm test
npm run typecheck
```

## License

MIT
