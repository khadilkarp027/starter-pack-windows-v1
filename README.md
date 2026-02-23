# Starter Pack — Windows v1 (AI L1 Agent Datasets)

This repository builds a **single ZIP bundle** containing small, public datasets to bootstrap a Windows‑only smart agent that:
- detects common L1 issues (disk space/health, performance, network),
- suggests guided self‑fix steps,
- and deep‑links users to your **Freshservice** portal (no log attachments).

The pack focuses on small, **fast‑to‑download** samples from reputable sources:

- **Windows logs (LogPai LogHub 2K sample)** – for log parsing & anomaly baselines. Full Windows set is 26 GiB and hosted via Zenodo; we only pull tiny samples here. [1](https://github.com/logpai/loghub)[2](https://zenodo.org/records/3227177)
- **Microsoft Sentinel sample SecurityEvent CSV** – clean CSV logs to validate event‑ID rules and ingestion. [3](https://github.com/Azure/Azure-Sentinel/blob/master/Sample%20Data/README.md)
- **EVTX example** – small Windows EVTX to smoke‑test EVTX parsing; see note inside `evtx_samples/`. [4](https://gigasheet.com/sample-data/sample-evtx)
- **Backblaze Drive Stats (one‑month CSVs)** – daily per‑drive SMART snapshots for disk‑health early warning. [5](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data)
- **CRAWDAD (IEEE DataPort)** – Wi‑Fi traces to derive connectivity troubleshooting motifs (requires free login). [6](https://ieee-dataport.org/collections/crawdad)[7](https://www.crawdad.org/)
- **Mendeley Help Desk Tickets** – real help‑desk CSV/XLSX; we reference small extracts for triage prototypes. [8](https://data.mendeley.com/datasets/btm76zndnt/2)

> **Why these sources?**  
> - LogHub is the de‑facto benchmark collection for AI‑driven log analytics (Windows, HDFS, OpenStack, etc.), with Zenodo mirrors and labeled sets for anomaly tasks. [1](https://github.com/logpai/loghub)[2](https://zenodo.org/records/3227177)  
> - Azure Sentinel provides official sample Windows SecurityEvent CSVs—ideal for rule validation before live collection. [3](https://github.com/Azure/Azure-Sentinel/blob/master/Sample%20Data/README.md)  
> - Backblaze publishes daily SMART data as CSV since 2013, perfect for on‑device disk health detection. [5](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data)  
> - CRAWDAD is the canonical wireless trace archive (now on IEEE DataPort). [6](https://ieee-dataport.org/collections/crawdad)[7](https://www.crawdad.org/)  
> - Mendeley’s help‑desk set enables early ticket categorization & “self‑fix likely?” experiments. [8](https://data.mendeley.com/datasets/btm76zndnt/2)

---

## Quick start

### Option A — PowerShell (Windows)
```pwsh
# from repo root
pwsh -File .\scripts\build_starter_pack.ps1
# result: starter_pack_windows_v1.zip
