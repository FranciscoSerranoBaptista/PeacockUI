# PeacockUI

**The business question:** can the people who own leadership development see what is changing across their leaders, and decide what to do next?

Analytics that only an analyst can read do not change a programme. PeacockUI is the console for [AquilaDB](https://github.com/FranciscoSerranoBaptista/AquilaDB) and [KestrelAnalytics](https://github.com/FranciscoSerranoBaptista/KestrelAnalytics). It puts the population on one screen, as a graph and as charts over time, so a leadership team can discuss the same picture.

This repository holds a description, screenshots and public issues. The source code is private.

## What a leadership function gets

- **One picture of the population.** The whole graph on one screen, coloured by community, level or theme, with filters.
- **Change over time.** Timelines over dates or over session numbers, distributions and comparisons, drawn on the points that are loaded.
- **An assistant that suggests, never decides.** It proposes a view or a chart for a pattern the analytics found, and shows the rule behind it. A person accepts or rejects it.
- **Review before anything counts.** Candidate findings wait for a human ruling before they become part of the record.
- **Safe by default.** The access key never reaches browser code. Sessions use an HttpOnly cookie, and writes are checked for origin.

## Screenshots

<!-- add images to docs/screenshots/ -->

## Built with

[cosmos.gl](https://github.com/cosmograph-org/cosmos) for the graph, [Unovis](https://unovis.dev) for charts, React and Vite.

## The stack

| Part | The business question it answers |
|---|---|
| **[AquilaDB](https://github.com/FranciscoSerranoBaptista/AquilaDB)** | Where do the records of development live, safely, over time? |
| **[KestrelAnalytics](https://github.com/FranciscoSerranoBaptista/KestrelAnalytics)** | What patterns hold across the population, and are they stable enough to act on? |
| **PeacockUI** | Can a leadership team see those patterns and decide what to do next? |

## Issues

Use the issues here for questions, ideas and collaboration requests. The working backlog is private.

© 2026 Francisco Serrano Baptista. All rights reserved.
