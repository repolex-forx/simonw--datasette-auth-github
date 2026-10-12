# Repolex Knowledge Graph of simonw/datasette-auth-github

RDF knowledge graph data for [simonw/datasette-auth-github](https://github.com/simonw/datasette-auth-github), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-auth-github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1d47f69f5a38e36e8b8a861d42b1a3b722b09e8e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1d47f69f5a38e36e8b8a861d42b1a3b722b09e8e
│           └── chunk-001.nq.gz
├── blob
│   ├── 211cc1db103639e03f39d3747088626effcaa61d.nq.gz
│   ├── 244e5caf2bbf0812dc8b8ec45a221ae73c1e8d36.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 38f436b901ab210ac1a0312eaffbe0d00e3dc26a.nq.gz
│   ├── 42577d7b31ded5f96e336bf9dce121b779f21865.nq.gz
│   ├── 4e19e4febd04263eef24838d640ac31d4cf847e7.nq.gz
│   ├── 655e2d7f26a3bed1bfb64209194784fdd33ec394.nq.gz
│   ├── 7a37debc062cfa3429a80f283714f057b0beaae3.nq.gz
│   ├── 85822775a1db47ad8404d0fa95899a4bd477349e.nq.gz
│   ├── 8c0000dd4fb686c883b55eb261c2a908f1b9fc7d.nq.gz
│   ├── 9d1f26915c164e749101f799f619e233d34b8e9c.nq.gz
│   └── b8a2a436b293016758b373603c0d35e3fb9ebbf4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1d47f69f5a38e36e8b8a861d42b1a3b722b09e8e.nq.gz
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

[simonw/datasette-auth-github](https://github.com/simonw/datasette-auth-github)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
