# Field Notes

`orbit-trade-fills-gate` is easiest to review by starting with the fixture, not the prose.

The domain cases cover `spread pressure`, `fill risk`, `portfolio drift`, and `quote width`. They sit beside the smaller starter fixture so the project has both a compact scoring check and a domain-flavored review check.

The widest spread is between `spread pressure` and `portfolio drift`, so those are the first two cases I would preserve during a refactor.

The language-specific addition keeps the review model in native test blocks.
