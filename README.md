# Repolex Knowledge Graph of python-trio/asyncgpio

RDF knowledge graph data for [python-trio/asyncgpio](https://github.com/python-trio/asyncgpio), parsed by [repolex](https://repolex.ai).

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
rlex download python-trio/asyncgpio
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9b35613b05ce8919886fa51259e9f0c8ab8a1ea3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9b35613b05ce8919886fa51259e9f0c8ab8a1ea3
│           └── chunk-001.nq.gz
├── blob
│   ├── 114c684ea2b0fb2b5452f97794eef84cb4e45dea.nq.gz
│   ├── 25c3ba4743af91d90f136fbd0385703bc7da7666.nq.gz
│   ├── 291bfeaa3b207e4173c50080f22cfb473363ee5a.nq.gz
│   ├── 2c329baa58452a0d4c35d7a2b2d134ecf0d4c98e.nq.gz
│   ├── 3ef924bc28e7803b4c5e6535106732290f26ea17.nq.gz
│   ├── 40487b883dac03b6190f2e2dee13ac1ae3895d4b.nq.gz
│   ├── 4368c04add01c12e6b9a621dfbaafab1d102c757.nq.gz
│   ├── 4b0b0543e7dd776158b6617a4a9028a4fef92744.nq.gz
│   ├── 4b4d29e336559b22be50220b87b11f82d5ced6c6.nq.gz
│   ├── 4d2ac78258a68514cda681c330038f480fde4a7f.nq.gz
│   ├── 4d3c092193517d5364a0198b60d1b0b599d568d8.nq.gz
│   ├── 4edd4b18b3f9a2893c3d0a37e5e747a5f09cebe7.nq.gz
│   ├── 51f3442917839f8e0f0cccb52b3c10968ad0779e.nq.gz
│   ├── 72716ab629f5ee1d8d5863b841b0292f03440a11.nq.gz
│   ├── 805d40244256c4c33c751fd68624c53bc6017b47.nq.gz
│   ├── 91a54725d2f58dc855d9753d02a3d080000f09f1.nq.gz
│   ├── 93836ead9b85bc440d120af69572e910c990d87e.nq.gz
│   ├── 9f38f8bea6ce8250fb7c1cfd429b453826ee4bcf.nq.gz
│   ├── a5c1ad2a27cde5be34e424a04352f9d221829fc4.nq.gz
│   ├── a9f1cf6ec328a9face723b1205e6fcbbbf62d041.nq.gz
│   ├── ab524c40998513019c5c18f9c63f52adba9cce71.nq.gz
│   ├── af0b5199450558a72cb4389f9b23a4bd614d4775.nq.gz
│   ├── b3fbdf1b2a3873988e86fa2afe11b429e5a076ba.nq.gz
│   ├── b4a495a03bce1a47f178390578e2ffca5a3bfadf.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── c0016d427acdb16f3959d514900e1c6cf1389bdd.nq.gz
│   ├── ca4bb52c17161b2d88309f64eb759250b04b72c6.nq.gz
│   ├── ce2369e8737b5f786595d9f3ae275bef3caa9898.nq.gz
│   ├── d2225958abdc1bab2fcfb9bfb770f107c3720b5a.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d874ae652deb673477c5228905f09b15aa7ed61d.nq.gz
│   ├── da6abdf2ce977fc22ed876f6b16a95a7fa4341da.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed31d2430663635315a1f99940a7f3d19dda8ed0.nq.gz
│   ├── f03b4712d31c4066b271a5bc534625c2c48178da.nq.gz
│   └── fb257b634d4d286e6a2e5821d3c738c376986721.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9b35613b05ce8919886fa51259e9f0c8ab8a1ea3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[python-trio/asyncgpio](https://github.com/python-trio/asyncgpio)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
