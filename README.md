# Repolex Knowledge Graph of cherrypy/tools-legacy

RDF knowledge graph data for [cherrypy/tools-legacy](https://github.com/cherrypy/tools-legacy), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download cherrypy/tools-legacy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f9f5337c8539cb23b01acc1aacae142c6e6f270b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f9f5337c8539cb23b01acc1aacae142c6e6f270b
│           └── chunk-001.nq.gz
├── blob
│   ├── 62cd0cbcfef90d89d99cb7bb555ef0c825c7b279.nq.gz
│   ├── afcee8326863bf4d33fe6f27442c5cc8b775ff6e.nq.gz
│   ├── b4787c3cf255271ee981837f480c9abf4d9325ea.nq.gz
│   ├── c110ef33420edc4d38f1968542bcee7488e71bfa.nq.gz
│   └── c5d580be49a303f3f9fe043d9353a5d602b04952.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f9f5337c8539cb23b01acc1aacae142c6e6f270b.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[cherrypy/tools-legacy](https://github.com/cherrypy/tools-legacy)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
