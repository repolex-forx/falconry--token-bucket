# Repolex Knowledge Graph of falconry/token-bucket

RDF knowledge graph data for [falconry/token-bucket](https://github.com/falconry/token-bucket), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/token-bucket
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 75bc464c275f53488a2e5d5029a75e0eaa679113
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 75bc464c275f53488a2e5d5029a75e0eaa679113
│           └── chunk-001.nq.gz
├── blob
│   ├── 23ce84e35723483096ebce9fcbe565c91fcebc7e.nq.gz
│   ├── 2cff64eb1842cfd75414b8e12d9003cc7385b1ad.nq.gz
│   ├── 3256be4b9894524865434df1ceac7cf6f1a82960.nq.gz
│   ├── 34a43d972dd728b4a9c2e78961e5ff53fec67784.nq.gz
│   ├── 4d36884a5b41b9c4150c33be60c87f3ca4cc0680.nq.gz
│   ├── 5c07db8beeab1f1a5feb7177f5a7aa2eb17d312d.nq.gz
│   ├── 8403c6d503ea09bea85264dbcfc6d34374334c60.nq.gz
│   ├── 9897f79940be0fc699be0b7cd73c605372917494.nq.gz
│   ├── c1797f89103df0476af638b5a546e262ba937e5e.nq.gz
│   ├── c71a6ee2279275bdb12da2f11ad9e6fca02cb40f.nq.gz
│   ├── d0915612c64842a4407b2cc937fae5fb20ef4136.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef1ececbaf0a1173105e02861099c443fc720ef4.nq.gz
│   ├── f85da10e2f92280087dc15400085d1613aacda3b.nq.gz
│   ├── fafff7410a69aca2d6f8a0b7fe2289b7d80c36b0.nq.gz
│   └── fca2acf886616660087169dc4a455c55ad662ca4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 75bc464c275f53488a2e5d5029a75e0eaa679113.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[falconry/token-bucket](https://github.com/falconry/token-bucket)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
