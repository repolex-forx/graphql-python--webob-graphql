# Repolex Knowledge Graph of graphql-python/webob-graphql

RDF knowledge graph data for [graphql-python/webob-graphql](https://github.com/graphql-python/webob-graphql), parsed by [repolex](https://repolex.ai).

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
rlex download graphql-python/webob-graphql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0c3fc392973272b76b796fd3afee970a07f9fad0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0c3fc392973272b76b796fd3afee970a07f9fad0
│           └── chunk-001.nq.gz
├── blob
│   ├── 0de3d9e2a57681298b0cbf5286a371b450f6fe30.nq.gz
│   ├── 211c150d22ea5eac760defa20c9a64e0acfd51ff.nq.gz
│   ├── 39a036a2cd29c34f1ae3ae98585591d3d354eb9e.nq.gz
│   ├── 3c0e42964018da5c5ce9c643f1d145f9c9296809.nq.gz
│   ├── 456b5f17f0582b269a707bda8581fc1dfb7e6559.nq.gz
│   ├── 48a24e883a588cc87e40db02c4cb958307910b94.nq.gz
│   ├── 52554b12f7440a86754a78a204d31dace2e3346d.nq.gz
│   ├── 5ad91dbe8e895c202e59bfdf7c2984aec2019b25.nq.gz
│   ├── 642f015bf654723c3863819074fc78c5dbe328a6.nq.gz
│   ├── 6a6be069861d34c2854970cf5ae4fca1343f1cfd.nq.gz
│   ├── 8785c3a35d69c8eaaaff46ee3a25cd02f45c4837.nq.gz
│   ├── a6342161056603c59987455927a17b012b77149b.nq.gz
│   ├── b6ff2043f2cc918fa4bdf6f3de58edf53146f133.nq.gz
│   ├── dbfe62783de62cafcad6a6f3a90f4e2f0e23634e.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0c3fc392973272b76b796fd3afee970a07f9fad0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[graphql-python/webob-graphql](https://github.com/graphql-python/webob-graphql)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
