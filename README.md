# Repolex Knowledge Graph of twisted/pydoctor_primer

RDF knowledge graph data for [twisted/pydoctor_primer](https://github.com/twisted/pydoctor_primer), parsed by [repolex](https://repolex.ai).

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
rlex download twisted/pydoctor_primer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8f597cfad43c64e0f6e1546cd9df39fd0771bf44
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8f597cfad43c64e0f6e1546cd9df39fd0771bf44
│           └── chunk-001.nq.gz
├── blob
│   ├── 37d72f9a8fbed984dc5aa6349a16892fb0c2f5d6.nq.gz
│   ├── 5030243e7a58272c84c8385dbd3404bc5bb0ae23.nq.gz
│   ├── 6a000697b75bae14aaca6692a4a569afefdccae1.nq.gz
│   ├── 7a806d8e554663fe6495f55ebba9c64f9ddbd9c1.nq.gz
│   ├── 9204538c58d722d44d363707a2e4aa15bc1a5e7a.nq.gz
│   ├── 94a87132f671a1b3dceddb009afc4b0a0e46e157.nq.gz
│   ├── a979a4df564b5bde2abd6d3552069ce8b516f1fc.nq.gz
│   ├── b2029e5aa7ad6bc87468f76be2e7697ef56dd98a.nq.gz
│   ├── b87fec1a1c0a084e934ef2def2f44aeb76fafbe6.nq.gz
│   ├── bb7159099d532395219ec212cc7261c9bc1af410.nq.gz
│   ├── bd3ecd1fff93f49c1eacf310350d433b8e59d021.nq.gz
│   ├── d161add17252f0e90c88ba9d547e5e9b29ba257e.nq.gz
│   ├── e598b6976c95167af891cfafa114a3b95c1e5631.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fa8c06f0bccce947d54fec45e23acb84b28579dd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8f597cfad43c64e0f6e1546cd9df39fd0771bf44.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[twisted/pydoctor_primer](https://github.com/twisted/pydoctor_primer)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
