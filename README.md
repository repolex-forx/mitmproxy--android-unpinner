# Repolex Knowledge Graph of mitmproxy/android-unpinner

RDF knowledge graph data for [mitmproxy/android-unpinner](https://github.com/mitmproxy/android-unpinner), parsed by [repolex](https://repolex.ai).

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
rlex download mitmproxy/android-unpinner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 60cbfee4d43cedaff622d72c27d87e418a111413
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 60cbfee4d43cedaff622d72c27d87e418a111413
│           └── chunk-001.nq.gz
├── blob
│   ├── 22e79c7b48e2fa595d1113058495284a722bdd66.nq.gz
│   ├── 38c18bdf922d985f99b091726cbc1564d7d5e432.nq.gz
│   ├── 4802e90f8edc38346215a3277cf96f0fa7474c32.nq.gz
│   ├── 7180b0f737ddbc41e678e0b183933712823be96a.nq.gz
│   ├── bffa70265f954852b10de42ffa6cc22c07f3e1dd.nq.gz
│   ├── ce22b3f2c0b09aa572dc6aaec7fd95556cad0b60.nq.gz
│   ├── cfc3c802dcddd25122b2ce1282ca63d76167a4e0.nq.gz
│   ├── eb9c709670c0f5daee5b68360eb8f43821b87857.nq.gz
│   ├── ee01db8446d798f1918f4600583f003e4c320f90.nq.gz
│   └── f58e9910bf7c240b7da7c3835b9f6e692d4ee1cf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 60cbfee4d43cedaff622d72c27d87e418a111413.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 17 files
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

[mitmproxy/android-unpinner](https://github.com/mitmproxy/android-unpinner)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
