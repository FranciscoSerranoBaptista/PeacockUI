# PeacockUI

**The research console for [AquilaDB](https://github.com/FranciscoSerranoBaptista/AquilaDB) and [KestrelAnalytics](https://github.com/FranciscoSerranoBaptista/KestrelAnalytics).** PeacockUI turns a graph database into a research instrument. A researcher starts from a question, reads a ranked answer, and keeps the question with its finding.

This repository is the public face of the project: the description, the screenshots and the public issues. The source code is private.

## The problem it solves

A force layout of a dense graph gives a hairball. The layout optimises the length of the edges, not the question of the researcher. A picture of several thousand points looks interesting and says little.

Investigative tools and science-mapping tools agree on a different loop. PeacockUI is built on it:

1. **Start from a question:** a seed, a selection or a saved query, not a whole collection.
2. **Expand within a limit:** one hop and one type at a time, with the count shown first.
3. **Read a ranked list or a histogram,** not only the layout.
4. **Select a subset and group the leaves.**
5. **Keep the question:** save the subset, the note and the finding as a named view.

## What it does today

- **Three workspaces:** the graph canvas, an AQL editor, and an assistant that turns a plain-English question into AQL.
- **Views that you can reproduce.** A view is a scope (what loads), a profile (how it looks) and filters (what shows). Saved views live on the server for each user, with a personal default and JSON export.
- **Kestrel on the canvas.** Colour by community, size by centrality, keep only the stable members, and run an analysis from the console.
- **An embedding map.** Points placed by meaning from a Kestrel projection, with the simulation off.
- **Community history.** The lineage of a point across runs, and a Sankey of community lineage.
- **Charts that filter.** Six chart types over the loaded points, with click-to-filter. On clinical data, a cohort floor of five applies and scatter plots are refused.
- **Suggested views** from the stored analysis runs.
- **A health panel.** A verdict for each data layer with ranked blockers. "Show" filters the canvas to the failing records.
- **Safe by default.** The access key never reaches browser code. Sessions use an HttpOnly cookie, and writes are checked for origin.

## What we are building now

The gap between a viewer and a research instrument is not an algorithm gap. The server already computes PageRank, Leiden with stability, community lineage, the embedding map, k-core, bridges, link prediction, `SURPRISE` and `JUSTIFY`. The console needs an entry point, a vocabulary and a memory. The work runs in this order.

**Change how the canvas is read:**

- **Seed and expand.** Start from a search, expand one hop at a time, and see the neighbour count before the canvas grows.
- **An ideas map.** Ideas placed by meaning, communities as pinned clusters, named regions, and faint links weighted by confidence.
- **Named communities.** A term label for each community, and a description from the assistant on demand.
- **A ranked list.** A new chart type: the top N points by any column, for example the top 20 ideas by PageRank.
- **Paths and provenance.** The path between two points with its weakest link marked, a drawer for each edge, and the chain that a point rests on.
- **Edges that count.** Weight and confidence drive the layout and the line width. A backbone filter keeps only the strong ties.

**Make the unusual visible and keep the question:**

- **Residuals, not magnitudes.** Size a point by what is unexpected for its class, and put a halo on the top few.
- **Queries bound to a selection.** Saved AQL that runs on the current selection: common neighbours, works cited by the selection, ideas close in meaning but far in the graph.
- **A question on each view.** A saved view keeps its selection and a note with the question and the finding.
- **A grouped view.** Communities as single nodes, and leaf points collapsed into a count.

**The research questions as views:**

- **Structural gaps:** pairs of communities that are close in meaning but not linked, with candidate bridges.
- **Ideas by decade:** communities per time window, linked by lineage, with the communities born in the last window.
- **Difference view:** two runs or two windows on fixed positions, with points added, removed and kept.
- **The trust plane:** surprise against grounding, as a scatter with four labelled quadrants.

**Data quality as a workflow:** a review queue for duplicate records that remembers each "does not match" decision.

## The two kinds of data

- **The research corpus** (works, chapters, ideas, concepts, traditions) is one connected graph. Graph views apply here.
- **The coaching data** is clinical, and each session is a small island by construction. A layout of it shows only islands. PeacockUI gives this data windows, tables and trajectories, under the cohort floor.

## Built with

[cosmos.gl](https://github.com/cosmograph-org/cosmos) for the graph, [Unovis](https://unovis.dev) for charts, React and Vite.

## The stack

| Part | Role |
|---|---|
| **[AquilaDB](https://github.com/FranciscoSerranoBaptista/AquilaDB)** | The engine: the records, their relations over time, and the privacy rules. |
| **[KestrelAnalytics](https://github.com/FranciscoSerranoBaptista/KestrelAnalytics)** | Graph and population analytics: communities with stability, centrality, statistics, pre-registered studies. |
| **PeacockUI** | The research console: start from a question, read ranked answers, keep the question with its finding. |

## Status

Ships with AquilaDB `v1.1.1`, the latest Aquila release (2026-10-12).

## Screenshots

<!-- add images to docs/screenshots/ -->

## Issues

Use the issues here for questions, ideas and collaboration requests. The working backlog is private.

© 2026 Francisco Serrano Baptista. All rights reserved.
