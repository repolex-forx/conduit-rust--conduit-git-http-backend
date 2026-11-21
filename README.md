# Repolex Knowledge Graph of conduit-rust/conduit-git-http-backend

RDF knowledge graph data for [conduit-rust/conduit-git-http-backend](https://github.com/conduit-rust/conduit-git-http-backend), parsed by [repolex](https://repolex.ai).

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
rlex download conduit-rust/conduit-git-http-backend
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7585b3bc433918c845264fca36a1d268e8f1b643
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7585b3bc433918c845264fca36a1d268e8f1b643.nq.gz
│   └── repolex
│       └── 7585b3bc433918c845264fca36a1d268e8f1b643
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1b88a9591c047c0e7bd153770944da7a4ceccc99.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 46366029837b11c7f34259655399bbbd355393f3.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── cd82017eaa559c9f89ff59e852cabed123ad3ba9.nq.gz
│   └── ef37c427bb04e60a06b59dbc9da5f18b58dbf205.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7585b3bc433918c845264fca36a1d268e8f1b643.nq.gz
├── filetree
│   └── 7585b3bc433918c845264fca36a1d268e8f1b643.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 17 files
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

[conduit-rust/conduit-git-http-backend](https://github.com/conduit-rust/conduit-git-http-backend)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
