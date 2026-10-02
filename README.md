# Repolex Knowledge Graph of block/melipona

RDF knowledge graph data for [block/melipona](https://github.com/block/melipona), parsed by [repolex](https://repolex.ai).

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
rlex download block/melipona
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 910fa5882da2f1f7ae04798c0592e893c9e745cf
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 910fa5882da2f1f7ae04798c0592e893c9e745cf.nq.gz
│   └── repolex
│       └── 910fa5882da2f1f7ae04798c0592e893c9e745cf
│           └── chunk-001.nq.gz
├── blob
│   ├── 0086358db1eb971c0cfa8739c27518bbc18a5ff4.nq.gz
│   ├── 0c5722b9da100bde3791980dc992ea383285e639.nq.gz
│   ├── 1fc95806a9cdb13ff526604cc3e486a78505f4c4.nq.gz
│   ├── 21d0198d0d2a1fe15bd7edeb704f034e494ce4a6.nq.gz
│   ├── 29b93a525e72489585c4b9d7fdb307d5741ed461.nq.gz
│   ├── 2a5388392db824bbdb8942aad96f3d8c9cc19720.nq.gz
│   ├── 326c6aa1cec485c69c654b8367643e7eb88a994c.nq.gz
│   ├── 34906f8ea18f7a4448de049b276fa27838e391e4.nq.gz
│   ├── 4b9c671659e3829b94154a8715f3cedac7066561.nq.gz
│   ├── 501dc0ff03e4e1581e4cdf43bd67b79a113f5fb7.nq.gz
│   ├── 54a750148f36ee314e8d7803a8a14296a22a825b.nq.gz
│   ├── 62af7e6564a0683ed21eaf86968691f63120a9e2.nq.gz
│   ├── 67e8f4917c8e961ea7fd014f03736491b618ad2b.nq.gz
│   ├── 6a8e883a479dbe406138b793797eede3cec0a67e.nq.gz
│   ├── 6af472fcfb47791c91e1fbdb2a47a174b341b30f.nq.gz
│   ├── 6b902c81a556d97fe0bb06c542e5e79f8b5c3ce1.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 6e9aa3bfd9dd6b9f497c03febfcaf2358493cd33.nq.gz
│   ├── 7a98a51b9b30bd2f302d2a4edd9a4b8750d0def2.nq.gz
│   ├── 862ee3c28647e7a58801a75236855c269c1448ae.nq.gz
│   ├── 8dc9b6f54d1630822e384aab9c5a2e721ea8fcb8.nq.gz
│   ├── 93d8d023102f8dcd6f4e83fe44a1231decaa7cd3.nq.gz
│   ├── 9582fc588754f78d9875691a3bd5e674295436b3.nq.gz
│   ├── 9cbd4a2e9f49d9dad973173120deb7ddb8c30c38.nq.gz
│   ├── a5e6093b6aab45a456220f7c88af407e8c1cb6b6.nq.gz
│   ├── c18722fbae72a030e35fed0558cf17a52accabba.nq.gz
│   ├── c2f8b5e7149a70f07950f81eaa3a26ccb4eabbaa.nq.gz
│   ├── d3138930b9fb39595811ee7e55b7597ca1191958.nq.gz
│   ├── d3ebf718940a53b92c2a1e663a1ef9813dd48097.nq.gz
│   ├── d5bd70701c5c94fc96bd491b86ad5c6e15639c4e.nq.gz
│   ├── d6b98fbabe949a601fe332f7cd3788ab2b33b31e.nq.gz
│   ├── dd81c11917529725c6a64d2c18927f758c03cfad.nq.gz
│   ├── e3f21d7a9abc43410346758f74b354e316d1fc9b.nq.gz
│   ├── e66ab5e2be4c245364b37046ba4b86f944908c3c.nq.gz
│   ├── e6fc77ff36e50723e9e5a8f8bfba8664f6f517ea.nq.gz
│   ├── f1029e910776af7d8e77b3a24cfe6f2dd17dbff1.nq.gz
│   └── f5ac9ec83066a979bc45e9d11ec597496055cf0e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 910fa5882da2f1f7ae04798c0592e893c9e745cf.nq.gz
├── filetree
│   └── 910fa5882da2f1f7ae04798c0592e893c9e745cf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 47 files
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

[block/melipona](https://github.com/block/melipona)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
