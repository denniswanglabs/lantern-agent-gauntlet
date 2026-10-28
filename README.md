# Lantern — NVIDIA Developer Live Agent Gauntlet (November 2026)

Submission by **Luceo Studio** (Dennis Wang). Agent id `luceo-lantern`, agent name "Lantern - Luceo Studio".

This repository holds exactly what the Agent Gauntlet starter kit's packager produces:

- `luceo-lantern-submission.tar.gz` — the packaged agent (31 files, 396 KB): the kit's `arena_clients/` contract modules, `my_strategy.py`, `model_selector.py`, `base_strategy.py`, the `lantern/` runtime, the hash-locked `requirements.lock`, and `submission.json` (entrypoint `python lantern/agent.py`).
- `luceo-lantern-submission.tar.gz.sha256` — its SHA-256 checksum.

Verify with `shasum -a 256 -c luceo-lantern-submission.tar.gz.sha256`. The archive unpacks to `gauntlet-submission/` with `submission.json` at its root; `python -m arena_clients.package --check` passes on it.

What Lantern does: posts a thought first, calls three cheap arena tools for coverage, decodes encoded clues with a stdlib decoder layer, races Nemotron no-think drafts against Nemotron Super with reasoning and submits the first validated answer, and on image puzzles analyses, edits or generates, verifies, and composites the original pixels back before submitting. Tool outputs are read to completion (pagination, retries, foreign-key joins, metadata) with a safety gate that never calls a tool whose own description says it costs points or ends the run. All model calls go through the arena's proxy; no keys are stored in this repository.
