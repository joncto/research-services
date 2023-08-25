---
title: Gephi
layout: home
nav_order: 5
---

*This section demonstrates how you can import data from SolrWayback to Gephi and visualise the data. However, NWA do not provide any support for this software. If you want to learn more about the many possibilities for network analysis in Gephi, please visit [Learn how to use Gephi](https://gephi.org/users/).*

# Gephi

Gephi is an open-source software for network analysis and visualisation. It is used in a number of projects, both inside and outside of adademia, e.g. in studies of Twitter network traffic during the terror attacks in Norway, 22 July 2011.[^1]

Before you start, you will need to export data from SolrWayback. See [Link graph Gephi export](./solrwayback/solrwayback-5export.md#export)

## Chapters
This section is divided into the following subchapters:



## Open Gephi
Go to the desktop and double-click the Gephi icon.

## Import data from SolrWayback
Go to "File" -> "Open".

Select a .csv file and click "Next" -> "Finished" -> "Ok"

## Overview tab
See #nodes in top right corner.

**Warning:** If more than 10.000 nodes, consider: filter tab (right), open topology, drag "giant component" down to filters. Click "filter".

## Select layout
Select "Yifan Hu" as your layout. Click "Run" and wait.

Repeat and clicking "Run" until you are happy with how the graph looks.
(For graphs with 1 million nodes, this can hours. So you are strongly encouraged to use filtering to scope down the amount of nodes!)

## Statistics
"Statistics" > "Network diameter" > "Modularity"

## Modularity class
Nodes, color palette, partition, modularity class

## subtitle
label size (tT), ranking, "Betweeness centrality", apply (change min/max, rerun)

## Preview
Preview > Refresh

## Export graph
Export SVG/PDF/PNG

[//]: # (## Further utilisation: If you export as an SVG, it is possible to use the [GraphPresenter]() [^2] to convert SVGs into an interactive, zoomable image in a browser. At the moment, this is not supported in NWA's virtual environment.)



----

[^1]: [Aouragh, Miriyam (2011), "Collateral Damage: #Oslo Attacks and Proliferating Islamophobia", Jadaliyya](https://www.jadaliyya.com/Details/24298/Collateral-Damage-#Oslo-Attacks-and-Proliferating-Islamophobia).
[^2]: [GraphPresenter is a tool, developed by the Royal Danish Library]