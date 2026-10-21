# Repolex Knowledge Graph of pandas-dev/.github

RDF knowledge graph data for [pandas-dev/.github](https://github.com/pandas-dev/.github), parsed by [repolex](https://repolex.ai).

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
rlex download pandas-dev/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5680a17581c44f1ed09b19a99d6e044295750d35
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5680a17581c44f1ed09b19a99d6e044295750d35
│           └── chunk-001.nq.gz
├── blob
│   ├── 085b0778b5af48391fd435a00ca5ae1d92a7dc65.nq.gz
│   ├── 27dfded808b952f912f8c30d46bff163bc21e456.nq.gz
│   ├── a623de3667bd2b93be7929e9f2603e977544b6cf.nq.gz
│   └── d27eab5b9c95cb2ce385bf9a39d42551155fa266.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5680a17581c44f1ed09b19a99d6e044295750d35.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 12 files
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

[pandas-dev/.github](https://github.com/pandas-dev/.github)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
