# Review Journal

The review surface for `orbit-trade-fills-gate` is deliberately narrow: one fixture, one scoring rule, and one local check.

The local checks classify each case as `ship`, `watch`, or `hold`. That gives the project a small review vocabulary that matches its trading systems focus without claiming live deployment or external usage.

## Cases

- `baseline`: `spread pressure`, score 226, lane `ship`
- `stress`: `fill risk`, score 168, lane `ship`
- `edge`: `portfolio drift`, score 105, lane `watch`
- `recovery`: `quote width`, score 130, lane `watch`
- `stale`: `spread pressure`, score 240, lane `ship`

## Note

The repository should be understandable without pretending it is larger than it is.
