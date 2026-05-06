# orbit-trade-fills-gate

`orbit-trade-fills-gate` is a Zig project in trading systems. Its focus is to design a Zig verification harness for fills systems, covering incremental indexing, append-only fixtures, and failure-oriented tests.

## Problem It Tries To Make Smaller

I want this repository to be useful as a quick reading exercise: fixtures first, implementation second, verifier last.

## Orbit Trade Fills Gate Review Notes

`stale` and `edge` are the cases worth reading first. They show the optimistic and cautious ends of the fixture.

## Working Pieces

- `fixtures/domain_review.csv` adds cases for spread pressure and fill risk.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/orbit-trade-fills-walkthrough.md` walks through the case spread.
- The Zig code includes a review path for `spread pressure` and `portfolio drift`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Design Notes

The repository has two validation layers: the original compact policy fixture and the domain review fixture. They are separate so one can change without hiding failures in the other.

The Zig implementation avoids hidden state so fixture changes are easy to reason about.

## Example Run

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Tests

The same command runs the local verification path. The highest-scoring domain case is `stale` at 240, which lands in `ship`. The most cautious case is `edge` at 105, which lands in `watch`.

## Known Limits

This remains a local project with deterministic fixtures. It does not depend on credentials, hosted services, or live data. Future work should add richer malformed inputs before widening the public API.
