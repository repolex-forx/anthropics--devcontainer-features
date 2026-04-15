# Repolex Knowledge Graph of anthropics/devcontainer-features

RDF knowledge graph data for [anthropics/devcontainer-features](https://github.com/anthropics/devcontainer-features), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download anthropics/devcontainer-features
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1d3f32d3a6f4a7cce4336a911978379e4aad8de5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1d3f32d3a6f4a7cce4336a911978379e4aad8de5.nq.gz
│   └── repolex
│       └── 1d3f32d3a6f4a7cce4336a911978379e4aad8de5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0717cc623b12a76201a4bf8641bd079b3e1a4cb7.nq.gz
│   ├── 0c894f085df164d35458a3b7a91d79f0b4f58164.nq.gz
│   ├── 22f41c16b03c811cdade36f1e7e94058e1a00df1.nq.gz
│   ├── 2e21845d8676024e2a609e306c33c2d60921368e.nq.gz
│   ├── 36f0d024c62ec6c57cb48d2a657ad7c5cf21849d.nq.gz
│   ├── 431d2a48876fe439966734d3fab5a0d5c6796b1a.nq.gz
│   ├── 45166e59bc578520669df280913624909bc92131.nq.gz
│   ├── 57c3de2263c24728ea4b58e56ebeb0ae13d5edc8.nq.gz
│   ├── 6aa44dfeabc2a63e09eb3f2d40c52aea98f8f651.nq.gz
│   ├── 8a7a84bf32538735e1341a4a020c9ba80bb8d3e1.nq.gz
│   ├── 8f2ece7e920485e053b888d0c788e7df3cdf6ac2.nq.gz
│   ├── f546f57db255f34f5f8db0c57368c508448941d5.nq.gz
│   └── f9a8428e9d6fef44767aa22a88162ff05f129d52.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1d3f32d3a6f4a7cce4336a911978379e4aad8de5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 22 files
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

## Source repository

[anthropics/devcontainer-features](https://github.com/anthropics/devcontainer-features)

---
*Parsed on 2026-04-15 by [repolex](https://repolex.ai)*
