# Repolex Knowledge Graph of sympy/sympy-bot

RDF knowledge graph data for [sympy/sympy-bot](https://github.com/sympy/sympy-bot), parsed by [repolex](https://repolex.ai).

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
rlex download sympy/sympy-bot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 497288b56304aaf61cf5f4f32320b7e9f0033f6f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 497288b56304aaf61cf5f4f32320b7e9f0033f6f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0555f9f4b4dd18c741bce724294d048e4cbede6f.nq.gz
│   ├── 2a87af593e77f0ecfb696323354e7419ebd071f0.nq.gz
│   ├── 2f787c257f7871db65023afc7c39800235b9340d.nq.gz
│   ├── 5379119160652d4520753cb864467a34073ce590.nq.gz
│   ├── 5383b4463cff7b75de7126c2a3fc91558e941cdd.nq.gz
│   ├── 549ab44bd09ea3d2e03de224f0f6ce4aafb4dfc6.nq.gz
│   ├── 5664e303b5dc2e9ef8e14a0845d9486ec1920afd.nq.gz
│   ├── 584743fb8fab14043132bc0435636b807d728ef9.nq.gz
│   ├── 5b28518332a20a73d47beb3fe973cd6292bf42b6.nq.gz
│   ├── 5e4029386af15d40ce3bb23eb1654c627fa78c49.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 72f1befc96bb6f9cdb64ede36aa7ce840c162ee2.nq.gz
│   ├── 85afc09acd7b2cb8b1770d95787078795e1eda05.nq.gz
│   ├── 98f6c50b1725b61a1f601ce9dab394a4b62ca341.nq.gz
│   ├── 9e818afa68538cdfb18e91cf37cf51ec7df8fd7d.nq.gz
│   ├── a570e0b9852312d13f8ebd0d552a4326fff1df2c.nq.gz
│   ├── b2691b9ea3ce9b12f3a1728f1da8f6a917dd8e37.nq.gz
│   ├── bdb0505b8c1a1f437b1816541f62507678b8f34b.nq.gz
│   ├── bdda8ab495713a360db6a6c7247a5befe60bd19e.nq.gz
│   ├── c177dd2fbf8ffc95ec5edcea5f1b8175bd39144d.nq.gz
│   ├── c5dc468fad2b312d90a31bf7f893a3ef9222991a.nq.gz
│   ├── ca72b1e046f04514c8106550f19f006cdfa8f53c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ee29a3034eaa3f76c4fa7934b5abeef7cdaba642.nq.gz
│   ├── f54571fba4129cabb7f5f9620be623975229ff3d.nq.gz
│   ├── f8a8f57126f99e2ad4623aae9242337baba4a32a.nq.gz
│   ├── faa5353ff7a7b8fb20c629f554d84bc1b748aae1.nq.gz
│   └── fdcc1cabf1a41dd21dd0e633327d14193cf44d9b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 497288b56304aaf61cf5f4f32320b7e9f0033f6f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[sympy/sympy-bot](https://github.com/sympy/sympy-bot)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
