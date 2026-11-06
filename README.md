# Repolex Knowledge Graph of scipy/scipy-release

RDF knowledge graph data for [scipy/scipy-release](https://github.com/scipy/scipy-release), parsed by [repolex](https://repolex.ai).

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
rlex download scipy/scipy-release
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 924bf365cc5cbb39200fb7d565daa2e876b5dd1d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 924bf365cc5cbb39200fb7d565daa2e876b5dd1d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c1119e0c173a0abc8fe397e70d75699c4f57e52.nq.gz
│   ├── 1032aece8a8109d67f238de6865d8b08e750a8c0.nq.gz
│   ├── 1147c6df6589e24962b9c4a578ce148c14c9a45f.nq.gz
│   ├── 11fcfefdbd0ef80a9984e4078c6d202ac894aea0.nq.gz
│   ├── 218676baa1899adb89dac086c88fc46ba0e6c90f.nq.gz
│   ├── 4e0626710d8af481477e902cea6ab775fa0e6c9f.nq.gz
│   ├── 4ec1ba55b2df2b5ffcc4221d91c7d87150dd2205.nq.gz
│   ├── 54744f60b90a9c2f3f9e9c786c5bafd5c3ee6906.nq.gz
│   ├── 5d3b1e2f296b35e7ab56e4b2e9f3d61a4ff94ccc.nq.gz
│   ├── 5edc44f71451f98d5f2d8344951d796ba3cfd567.nq.gz
│   ├── 715d7ae95f336b0aa7c3ea3242cc93dd0f1d4cb4.nq.gz
│   ├── 7ea6cf2ebb5e36f6104eaef661e36a9a28ef70dc.nq.gz
│   ├── 7f7777b6f8e7b95f2e5b229525f36b0ff9bc9e84.nq.gz
│   ├── 8c6c98fba4e1e5e925809f8b43be2394d74b56a5.nq.gz
│   ├── 94806c79e0583e2fd9aeea5b446360ca638bdee9.nq.gz
│   ├── 952bd45831b7ade4b37dbaa934d0f74fdd2b88e2.nq.gz
│   ├── c1c20e312aad3a2c01c6e572d6bcd7eb87b9380b.nq.gz
│   ├── c2ab513da043eb570707d59af512090c4465b30a.nq.gz
│   ├── ce7214af49fcc7e502d1e933c197cd6b07bc7534.nq.gz
│   └── f3772e49751ef388b6d5a57afb1d886592562175.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 924bf365cc5cbb39200fb7d565daa2e876b5dd1d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[scipy/scipy-release](https://github.com/scipy/scipy-release)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
