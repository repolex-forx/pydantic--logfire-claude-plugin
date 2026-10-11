# Repolex Knowledge Graph of pydantic/logfire-claude-plugin

RDF knowledge graph data for [pydantic/logfire-claude-plugin](https://github.com/pydantic/logfire-claude-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/logfire-claude-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3da608785db7f5a6440a7f8a66ed5145dc1e15e6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3da608785db7f5a6440a7f8a66ed5145dc1e15e6
│           └── chunk-001.nq.gz
├── blob
│   ├── 2c0083e001b3e2ea2a3dd08433a6a18c8ca65d61.nq.gz
│   ├── 389496be485e4bf22ebcaf584a77fd64ad5f2532.nq.gz
│   ├── 4a3bf3ca771de084e122effd3691333a26ea4cca.nq.gz
│   └── 4fe332b5fb5a577d8d7eb8e8d9222c75281b992a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3da608785db7f5a6440a7f8a66ed5145dc1e15e6.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 10 files
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

[pydantic/logfire-claude-plugin](https://github.com/pydantic/logfire-claude-plugin)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
