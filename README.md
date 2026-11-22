# Repolex Knowledge Graph of dtolnay/no-panic

RDF knowledge graph data for [dtolnay/no-panic](https://github.com/dtolnay/no-panic), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/no-panic
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1d85feca150ee7e1356794ab17c7be10fecaac54
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1d85feca150ee7e1356794ab17c7be10fecaac54.nq.gz
│   └── repolex
│       └── 1d85feca150ee7e1356794ab17c7be10fecaac54
│           └── chunk-001.nq.gz
├── blob
│   ├── 01ad392e1a08024bfeb37de7fa1c02d3e23b4e53.nq.gz
│   ├── 16c4c810d035f6342d321ab05fadc4c86ef1b5c6.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3b71c6eebbf48f03e7af388bb95b871d0fc9ce35.nq.gz
│   ├── 3dbec212edfbdc68a97aa1aea32aae2a793c1ce7.nq.gz
│   ├── 5e8be6ecea825c7a99f140dd65c6fbf771a8eeb1.nq.gz
│   ├── 650d01a100a146e3e3c6d191d05b37336c5e2aae.nq.gz
│   ├── 65deada23ac18d176fe74405eae410b4064d8277.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 76219eb72e8524f15c21ec93b9b2592da49b5460.nq.gz
│   ├── 88d1a9516bfe285d6a42ed6af4b81a11405c4abe.nq.gz
│   ├── 89da6ef251f07d664712a0041d5eef0ea7a6a644.nq.gz
│   ├── 8c025383b0d2faec751d2935a9080096712ae261.nq.gz
│   ├── 965b606f331b51d566b46025f9ff311a7aad0c12.nq.gz
│   ├── 9666aae319af2e641ef57a61306a9a31e209c4b3.nq.gz
│   ├── ad06ecc06a454c4e676c7d3c566c36c3162fac52.nq.gz
│   ├── b4215c8ae08042851ca7aab32d4ff06069dce476.nq.gz
│   ├── c3026e6e46f8faa108679bc527c38e3183230a53.nq.gz
│   ├── d1baefe7524b16f8747e3aebf9fc14e939008e04.nq.gz
│   ├── d2c650fb1f387d5ffce343c31bfa7d77c59ab3ce.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   ├── ebaa409a421ac6eb7b6790873103a5375c648262.nq.gz
│   └── eea5b0559138a442567f02526e045f17640960de.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 1d85feca150ee7e1356794ab17c7be10fecaac54.nq.gz
├── filetree
│   └── 1d85feca150ee7e1356794ab17c7be10fecaac54.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 34 files
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

[dtolnay/no-panic](https://github.com/dtolnay/no-panic)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
