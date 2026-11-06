# Repolex Knowledge Graph of sphinx-contrib/paverutils

RDF knowledge graph data for [sphinx-contrib/paverutils](https://github.com/sphinx-contrib/paverutils), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/paverutils
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5e94ec59ffa5ae3fd0bff99c0389c3349ae42263
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5e94ec59ffa5ae3fd0bff99c0389c3349ae42263
│           └── chunk-001.nq.gz
├── blob
│   ├── 0edbca75c912ca219557f62daef8d7606385322b.nq.gz
│   ├── 27a5330b3094ddfe061b55ae193a0d8dc77fe8f4.nq.gz
│   ├── 6583868fdd03dfd486e961a2db30dc883e313a9f.nq.gz
│   ├── 7a1392c5998a3a6231fb94f7617307fc930a0947.nq.gz
│   ├── 811ae3aef790f3985c2c0b9882a8ee7fba672a32.nq.gz
│   ├── 8133e2ad9387c498c571ab240d899ccb01acd666.nq.gz
│   ├── 87d259b7cd3416f66eb93948a81ce055b45b24b3.nq.gz
│   ├── 9c860a50349d4e035d070a60087ad3bb7e69495e.nq.gz
│   ├── 9d4c12760f3c50e7c750c975dd5754cb350f54cf.nq.gz
│   ├── ab37a650168c4fa880d88e1ed99bd5d2ed2d36e8.nq.gz
│   ├── ea49da94e4179733cdcbe8ee39e5f13966b6e03e.nq.gz
│   └── ec7b1091481e489201d9ad4c333c336c4ede0a8c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5e94ec59ffa5ae3fd0bff99c0389c3349ae42263.nq.gz
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

[sphinx-contrib/paverutils](https://github.com/sphinx-contrib/paverutils)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
