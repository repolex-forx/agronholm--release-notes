# Repolex Knowledge Graph of agronholm/release-notes

RDF knowledge graph data for [agronholm/release-notes](https://github.com/agronholm/release-notes), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/release-notes
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d1772d33a8f22913df34832b21ae64dd95e73a0e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d1772d33a8f22913df34832b21ae64dd95e73a0e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f9a642b42bc96a1bb939902a2255d0f09c53f32.nq.gz
│   ├── 3da0ee0d2b2aa78dbd82a3b794c74f7d8687f0c2.nq.gz
│   ├── 48c953585da879d296160b65146b93adf2c6ae31.nq.gz
│   ├── 49042497c322fd47493656317fcf009385cf2e6d.nq.gz
│   ├── 4a3462dc7e0474b4480cb000361db60337b7d9cb.nq.gz
│   ├── 58e498aef9cf9e07be508ee29f7130fcc2f88c3d.nq.gz
│   ├── 8f9fe4fb79414ca5a2c2ddd8057dcdd20a3f413b.nq.gz
│   ├── 92d81be6b49ba323e748b2afa9dd5674583ae96a.nq.gz
│   ├── a60a8cb9e88b8ef8e3cd0cc50f94d90671ed9396.nq.gz
│   ├── ddb458a8aa9e3026588de3b89cf35ba24fa3921b.nq.gz
│   ├── e8f01df34f851f95b7daea8a26191db07872fec1.nq.gz
│   └── efe94069755aa824a1fbc1a1312a6f3f9f94c8da.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d1772d33a8f22913df34832b21ae64dd95e73a0e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[agronholm/release-notes](https://github.com/agronholm/release-notes)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
