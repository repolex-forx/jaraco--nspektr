# Repolex Knowledge Graph of jaraco/nspektr

RDF knowledge graph data for [jaraco/nspektr](https://github.com/jaraco/nspektr), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/nspektr
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5d29faa1f92054fe0a600a2f90b03365b0a3221d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5d29faa1f92054fe0a600a2f90b03365b0a3221d
│           └── chunk-001.nq.gz
├── blob
│   ├── 10d412f406891b9683f832fcbc134c9bdf4f916e.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 63d81881a6452104bd03336815ae1b28c5a4ea05.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 986d1aeb8414bfe71183d126ed7f178a54c98477.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── b459b588083fb6b0e62e59bd76cad10b29aa6f94.nq.gz
│   ├── c38a9869a4c9db2b4ccc5aec1dd2f712725c4a2e.nq.gz
│   ├── cae156a3c24ffb175df125c214a27be88da68f3a.nq.gz
│   ├── da183cda84eff1c21055536018169417ba378e7b.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e9a7a12e177e49dfc3715f8a59082e67562d7815.nq.gz
│   └── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5d29faa1f92054fe0a600a2f90b03365b0a3221d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[jaraco/nspektr](https://github.com/jaraco/nspektr)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
