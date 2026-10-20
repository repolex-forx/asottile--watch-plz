# Repolex Knowledge Graph of asottile/watch-plz

RDF knowledge graph data for [asottile/watch-plz](https://github.com/asottile/watch-plz), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/watch-plz
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 16c33861a7b32ac359d4e2c972d302095a99da77
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 16c33861a7b32ac359d4e2c972d302095a99da77
│           └── chunk-001.nq.gz
├── blob
│   ├── 95fc7f8c59085e020d69d3e3ec7e37c3670578b8.nq.gz
│   ├── e03e944532a11962fd394d18a60221fb9943e5f7.nq.gz
│   ├── ea8ea9b18ee9588dd1a3f92bdf04aaa23c6c208e.nq.gz
│   ├── ed2ce132dd6f53bd296bdc09219ab68a0de172a7.nq.gz
│   └── f1543fad215851e7e301b045b4b8f95a1e446d9c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 16c33861a7b32ac359d4e2c972d302095a99da77.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 12 files
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

[asottile/watch-plz](https://github.com/asottile/watch-plz)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
