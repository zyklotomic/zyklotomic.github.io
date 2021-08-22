---
title: Haskell.org GSoC 2021 Final Evaluation
layout: default
---

# Visualization Libraries for ghc-debug

### Google Summer of Code Project Link
https://summerofcode.withgoogle.com/projects/#6368742172262400

## Completed Work
- Added support for exporting the resulting graph from the
TypePointsFrom analysis to the GML graph visualization format: [ghc-debug merge request #3](https://gitlab.haskell.org/ghc/ghc-debug/-/merge_requests/3)

- Fixed a Hadrian (GHC build system) bug that prevented a GHC with
ghc-debug support being built on Darwin: [GHC merge request #6082](https://gitlab.haskell.org/ghc/ghc/-/merge_requests/6082)

- Added convenience functions for converting a generalized
census data type to Vega-Lite visualizations:
[ghc-debug merge request #4](https://gitlab.haskell.org/ghc/ghc-debug/-/merge_requests/4)

    - Converts a single census into a bar chart
    - Converts a series of censuses into a stacked area chart

- Support for outputing root traces as flamegraphs: [ghc-debug merge request #4](https://gitlab.haskell.org/ghc/ghc-debug/-/merge_requests/4), under `FlameGraph.hs`

- Attempted converting existing memory leak
detection methods from
[BLeak](https://cacm.acm.org/magazines/2020/11/248223-bleak/fulltext): [ghc-debug merge request #5](https://gitlab.haskell.org/ghc/ghc-debug/-/merge_requests/5)

    - Created functions to calculate total transitive closure size
    - Uses total number of closures transitively pointed to, to determine leaks
    - Characterizes leaks caused by lazy evaluation as long lists of the
    same kind of thunks


## TODO
- Adapt more of existing analysis functions to output to the generalized census type

- Continue experimenting with BLeak, to find the characterization that describes a memory
leak the best. Current linked list characterization is not sufficient.