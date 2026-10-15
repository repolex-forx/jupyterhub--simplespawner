# Repolex Knowledge Graph of jupyterhub/simplespawner

RDF knowledge graph data for [jupyterhub/simplespawner](https://github.com/jupyterhub/simplespawner), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/simplespawner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 86bd528fe1abed4592f296331fad98298f8398b4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 86bd528fe1abed4592f296331fad98298f8398b4
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a0669ea8b1dcde5e5210b7dcec0f933585c031e.nq.gz
│   ├── 1dbc687de014ee027b4e6c0d7f2a37ee7636137e.nq.gz
│   ├── 2c2fa751027e249a8981bccb11358c08ba1e683e.nq.gz
│   ├── 765bbb4850b0325a2cf9def22ff313e34f000224.nq.gz
│   ├── 8c64f0b417247f8824dd6213c89eb8d79bd78140.nq.gz
│   └── d43e97f47cad9fb5bc897ae5807f261ca8e91624.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 86bd528fe1abed4592f296331fad98298f8398b4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
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

[jupyterhub/simplespawner](https://github.com/jupyterhub/simplespawner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
