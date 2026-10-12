# Repolex Knowledge Graph of Pylons/pyramid_mailer

RDF knowledge graph data for [Pylons/pyramid_mailer](https://github.com/Pylons/pyramid_mailer), parsed by [repolex](https://repolex.ai).

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
rlex download Pylons/pyramid_mailer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e6b72508df2dde8101adb727d70d25f89a24164
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2e6b72508df2dde8101adb727d70d25f89a24164
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b32ec36fc72d31e0b5d389c31d93da1972e25e3.nq.gz
│   ├── 134b29a7a937a7684e5b5d2e0a46c9f0ee9c9c26.nq.gz
│   ├── 142b6ca357fee89f09803fc9ad7ff676500c37cf.nq.gz
│   ├── 1a196986af10956dc32ba49638454e27803d8427.nq.gz
│   ├── 1deca3cb894aed30e4bf9cbdac4d92071bddd26c.nq.gz
│   ├── 210723197abfdbaf24f90cb151ec19195cbd9799.nq.gz
│   ├── 213930e9350b45a4e0d677b7c9bc970b4f1f240e.nq.gz
│   ├── 358017656ed1e5da298404b291b0858d34d51bec.nq.gz
│   ├── 3cd7174a669ea5854a9237fbbad1c89d843241e8.nq.gz
│   ├── 471474fd284d78d65de52b5ec8be772a08eaf5de.nq.gz
│   ├── 4a7048960b51ca154e0bcf46e805263ecb285801.nq.gz
│   ├── 5bb534f795ae0f566ba9f57c31944d8c6f45284c.nq.gz
│   ├── 5c04332d747a685ca308c08f564bc6dc5317a504.nq.gz
│   ├── 614e090c1b882b18b1d99b514706ce1c0c31a6cf.nq.gz
│   ├── 736120c173930b9fc3619f0363d9805a7dcfee28.nq.gz
│   ├── 747b2452996e6ef3d956233e15a23419fefeb375.nq.gz
│   ├── 75ca1e320fb901f5e8852a0bd15e49e40b39eed5.nq.gz
│   ├── 7e164783755d6848a0324bcb317bea2564bcaa58.nq.gz
│   ├── 87d6003970b15f206680dc2f3b2ef17ea1421b00.nq.gz
│   ├── 8947fa903bf92f03b9f766a323cd433d5015d1ab.nq.gz
│   ├── 981e5611dd561989a5e51ab4d77666de232a8926.nq.gz
│   ├── 9d60ba964cc331103f53f465d7ba70ee778b368c.nq.gz
│   ├── 9e7fc5225f6b0033b7d2010d4714d33507e229a4.nq.gz
│   ├── a9a500e72143be090d5a2bdd1da9008499fe5135.nq.gz
│   ├── ae164e7267f079fc84acab3d88544cf5d413b598.nq.gz
│   ├── b2369e9b65e06021ce2540f131806e079da5d726.nq.gz
│   ├── bb7e3df98c6edd0a4417a2bc9e1745cc86d10e95.nq.gz
│   ├── cae0fd0f6c0189de3c461ba08ee78af8a09a0f1d.nq.gz
│   ├── cbb675424b24898d0493d0271e21bf8c06d64605.nq.gz
│   ├── d27c76f0f86c3c624898bc599c076f2b3cb249e0.nq.gz
│   ├── d6726d98d3c70c0d6f3001cd108af170f32042e9.nq.gz
│   ├── e1a6901ec1b4da43e71c99e27424a2ef03f2e0c2.nq.gz
│   ├── ea0bbb39bf54609a3aba51362aa9f529e3e6e0b3.nq.gz
│   └── eb43a07abdef5e4da5b59e13792448842766d40e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e6b72508df2dde8101adb727d70d25f89a24164.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[Pylons/pyramid_mailer](https://github.com/Pylons/pyramid_mailer)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
