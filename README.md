# Pustaka Terbuka — UMT (Universiti Malaysia Terengganu)

> **Pustaka Terbuka: Katalog Induk Terbuka untuk Perpustakaan dan Sekolah Malaysia.**  
> *Official Perpustakaan Sultanah Nur Zahirah (Universiti Malaysia Terengganu) (UMT) Bibliographic Dataset & Standalone Harvester.*

This repository contains the harvested open MARCXML collection and harvester pipeline for **Perpustakaan Sultanah Nur Zahirah (Universiti Malaysia Terengganu)** (`UMT`), contributing to the national Malaysian union catalog at [pustaka-terbuka/opac](https://github.com/pustaka-terbuka/opac).

---

## Institutional Metadata

| Attribute | Value |
| :--- | :--- |
| **Institution Code** | `umt` |
| **Agency Code** | `UMT` |
| **Official Name** | Perpustakaan Sultanah Nur Zahirah (Universiti Malaysia Terengganu) |
| **Institution Type** | `university` |
| **State / Territory** | Terengganu |
| **Classification Scheme** | `LCC` |
| **OPAC Base URL** | [https://psnz.umt.edu.my/](https://psnz.umt.edu.my/) |
| **Platform / Engine** | `koha` |
| **Default Branch** | Perpustakaan Sultanah Nur Zahirah (Kuala Nerus) |

---

## Directory Structure

```text
umt/
├── README.md                      # Institutional repository documentation
├── package.json                   # Node.js project specification & scripts
├── harvest/
│   └── inbox/umt/             # Sealed MARCXML batch chunks and manifests
│       └── <run-id>-chunk-001/
│           ├── manifest.json      # Chunk SHA-256 manifest & metadata
│           ├── provenance.jsonl   # Record-level attribution and fetch logs
│           └── records/           # Batched MARC21 slim XML files
├── tools/
│   ├── harvesters/umt/        # Automated OPAC crawler & MARC21 converter
│   ├── lib/                       # Supporting MARCXML, LCC, and validation utilities
│   ├── schemas/                   # JSON schemas for manifests and provenance
│   ├── validate-inbox.js          # Dataset integrity and schema validator
│   ├── merge.js                   # Local catalog merge engine
│   └── ingest-to-master.js        # Safe master ingestion bridge into pustaka-terbuka/opac
└── tests/
    └── harvester-umt.test.js  # Autonomous test suite
```

---

## Usage

```bash
# Install dependencies
npm install

# Test run harvester (10 sample records)
npm run harvest:sample

# Run harvester with chunking
npm run harvest:chunked

# Validate dataset integrity
npm run validate-inbox harvest/inbox/umt/<chunk-directory>

# Ingest new harvested batches into the central OPAC union catalog
npm run ingest:master
```

---

## Attribution & License

Dataset harvested and preserved under open library metadata standards for educational, civic, and cooperative indexing. Attribution: **Perpustakaan Sultanah Nur Zahirah (Universiti Malaysia Terengganu) (UMT)** & **Pustaka Terbuka**.
