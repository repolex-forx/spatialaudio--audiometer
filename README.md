# Repolex Knowledge Graph of spatialaudio/audiometer

RDF knowledge graph data for [spatialaudio/audiometer](https://github.com/spatialaudio/audiometer), parsed by [repolex](https://repolex.ai).

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
rlex download spatialaudio/audiometer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e631daefa2597f75ceec514a14d4974dee123265
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e631daefa2597f75ceec514a14d4974dee123265
│           └── chunk-001.nq.gz
├── blob
│   ├── 16df624944f2688a55ae06ef9da3aefcb78c5552.nq.gz
│   ├── 2298424f6c39d757cc229e4f57a0387390955669.nq.gz
│   ├── 2eb8148b3e95bf14791d94777ae04822c71b96fc.nq.gz
│   ├── 3567671e498585a2e46a11e803490884c788df7d.nq.gz
│   ├── 57b2840b4ceb4535c470972d11a9d33e5a69da66.nq.gz
│   ├── 70043b55dcab0931de3881072e9604797f1a521e.nq.gz
│   ├── 7c838f7e17f77607f581c65e52b68e5b6a64a8bf.nq.gz
│   ├── 9783fb34e006f2d639563ad8f2f22b336d251b3d.nq.gz
│   ├── ac8cef33c4f9330e7570e9be85f81aba5581dc50.nq.gz
│   ├── b30716c9d96e5ad90325478453227d1bf49c1a1c.nq.gz
│   ├── b3c068dd25ee1ec1de1c251dbdb35b2b61814012.nq.gz
│   ├── b895aff3201337114659cfab0c509f9b59a7b4ac.nq.gz
│   ├── ba34d3a4dc3fc80d14ce911ef1e1b6b16b9e1d13.nq.gz
│   ├── d2349a882d109d87bf99fddccf0249ed43463722.nq.gz
│   ├── dfb0449a107c1a3f4ceef9822f920d4be16dfa73.nq.gz
│   ├── e32b26da9855f23832632e0325f6f15512019816.nq.gz
│   ├── f776d89299357a11f2fb333ec75727b8a53af8ce.nq.gz
│   └── f88567e9e2ac2c851480a00026e559bb6905213a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e631daefa2597f75ceec514a14d4974dee123265.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[spatialaudio/audiometer](https://github.com/spatialaudio/audiometer)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
