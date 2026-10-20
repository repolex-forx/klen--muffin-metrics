# Repolex Knowledge Graph of klen/muffin-metrics

RDF knowledge graph data for [klen/muffin-metrics](https://github.com/klen/muffin-metrics), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-metrics
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b62fc25172e3e1e9fc6dc6c8da3170935ee69f01
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b62fc25172e3e1e9fc6dc6c8da3170935ee69f01
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 1db8128bdca363277b79af7b82d921f35357c266.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 4a4860650685fbbcbb86604c092bcb31df860293.nq.gz
│   ├── 5aae96c05508cd2a35f42796ae1ba37d3ea22e0b.nq.gz
│   ├── 5dc8caf457dfb634bfa221a45532792657e357f7.nq.gz
│   ├── 668a32d7458f99c44044e788fd737d3767a84c13.nq.gz
│   ├── 66e30de29e0e11e0ad160feada2d43b5714d7e71.nq.gz
│   ├── 6fa749b2dd9ec75df4a0842292d1e4d20f4c8755.nq.gz
│   ├── 8328b6621a29f503555767be58d297863f44331f.nq.gz
│   ├── 84a28244c53f1092d3081ffe270fd4477f6ca43d.nq.gz
│   ├── 9a690b3e50cc47bdd7bacf70b309626c141d5017.nq.gz
│   ├── 9abf7adc503f9a6d179531500a3d95609fec207b.nq.gz
│   ├── 9d5436b25ee9ac414b375a7efab049d425257ec6.nq.gz
│   ├── ac0cad773f102b57fad255f6b11a1476b1040691.nq.gz
│   ├── ad49bcb62264b823ca6e15e6074af33ba49626e9.nq.gz
│   ├── d44e0a45b04662184472eb2ea45dcd255cf6d444.nq.gz
│   ├── d830df0a67f8448f6322889b64918656f0ca38de.nq.gz
│   └── ff4017bee5abadf3bb00fb325460d33f37a19be5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b62fc25172e3e1e9fc6dc6c8da3170935ee69f01.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 25 files
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

[klen/muffin-metrics](https://github.com/klen/muffin-metrics)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
