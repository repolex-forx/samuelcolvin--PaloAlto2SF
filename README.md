# Repolex Knowledge Graph of samuelcolvin/PaloAlto2SF

RDF knowledge graph data for [samuelcolvin/PaloAlto2SF](https://github.com/samuelcolvin/PaloAlto2SF), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/PaloAlto2SF
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 98124cdbed195a237d1a1924dc7992d39f125538
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 98124cdbed195a237d1a1924dc7992d39f125538
│           └── chunk-001.nq.gz
├── blob
│   ├── 22a63b3a13b14fd3eb6f10c33444e82f5524a4f0.nq.gz
│   ├── cac4dfc51cea23455947e668891a04cb68eec941.nq.gz
│   ├── d5938407ab7c30d5922619be8bda8ed32f2fdefe.nq.gz
│   ├── da3c5f28aa1d34def0e5604db01400ee8970b501.nq.gz
│   └── e0e5162fbbc0186e20bc21b20953ce5998954b60.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 98124cdbed195a237d1a1924dc7992d39f125538.nq.gz
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

[samuelcolvin/PaloAlto2SF](https://github.com/samuelcolvin/PaloAlto2SF)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
