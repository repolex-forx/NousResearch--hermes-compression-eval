# Repolex Knowledge Graph of NousResearch/hermes-compression-eval

RDF knowledge graph data for [NousResearch/hermes-compression-eval](https://github.com/NousResearch/hermes-compression-eval), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-compression-eval
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b65773b401874863b3dab94d6b0bd3d19fd95688
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b65773b401874863b3dab94d6b0bd3d19fd95688.nq.gz
│   └── repolex
│       └── b65773b401874863b3dab94d6b0bd3d19fd95688
│           └── chunk-001.nq.gz
├── blob
│   ├── 06b856b9fe3ffa835f07fa1eda1b40d60ac08d93.nq.gz
│   ├── 20535c25d6d01b0f5dd6ae8387329ab526110627.nq.gz
│   ├── 2d2fb325bdb9808c39aac6424d71f82e263fa4dc.nq.gz
│   ├── 358be2ceece5c2bbb844affbcd1bf189e78f492d.nq.gz
│   ├── 3c9a13ab629e908895c4ff3a6aae0a22c0d04451.nq.gz
│   ├── 3dd11f9021e2dd80bf8ac300f5eb3fdf4ec925d4.nq.gz
│   ├── 3e039cf2fc96f9e072c653063ea28ec3cd76cfb1.nq.gz
│   ├── 4d84fcae295adcbe2dd4b033778ed53d1d8456f5.nq.gz
│   ├── 536c0992880940542ea97b89d932ef0ebedbe4db.nq.gz
│   ├── 53aa122a7f5853ec8967eae9d96e557f5cba0ca9.nq.gz
│   ├── 7fba1cb63ac04662fb8b36eac4cccee941732fe3.nq.gz
│   ├── 84b73d7d9c3eb5d37e9364c26011850a89a6ddf7.nq.gz
│   ├── 8ba5989ede86c1ae2dc1ac690cb12ae7be2852db.nq.gz
│   ├── b3a056d97b57673e23a9e97c4200780d6483d6f6.nq.gz
│   ├── b53814dc6adc61a61a75afb23539e67ddaed2960.nq.gz
│   ├── ca34e340d5c09b850e405af9dbaf43379df503cf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f359caaa4700fcbf87106b978a5343b9cf619d85.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b65773b401874863b3dab94d6b0bd3d19fd95688.nq.gz
├── filetree
│   └── b65773b401874863b3dab94d6b0bd3d19fd95688.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 27 files
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

[NousResearch/hermes-compression-eval](https://github.com/NousResearch/hermes-compression-eval)

---
*Parsed on 2026-10-04 by [repolex](https://repolex.ai)*
