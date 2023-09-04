---
title: SolrWayback
layout: home
nav_order: 3
has_children: true
permalink: /docs/solrwayback
---

# SolrWayback

SolrWayback is a service offering advanced exploration of the Norwegian Web Archive.
{: .fs-6 .fw-300 }

SolrWayback's features include:
- Full-text search
- Metadata search
- Image search
- Features for insight and analysis
- Export of search results

## Table of content
1. [Get started](./solrwayback/get-started)
2. [Search](./search)
    a. [Search modes](./search/search-modes)
    b. [Search synthax](./search/search-modes)
    c. [Field descriptions](./search/fields)
3. [Features & Tools](./features)
4. [Export search results](./export)

## Credits
SolrWayback is a bundle of different technologies, developed and maintained by the Royal Danish Library.[^1]

## Version
Current installation of SolrWayback is version 4.4.2


## Scope of data
For the workshop, we have indexed selected collections, harvested after 2019. The data is about 11TB, which is about 40% of the data between 2019-2022, and 0,5% of all data recorded since 2000.

The collections are:

|||||
|--- |--- |-- |--- |
|**Collection**|**Period**|**Description**|**Number of objects**|**Data size**|
|`noall`|2019-22|Domain crawls of .no|no.obj.|7.5TB|
|`samisk`|2020-22|Sámi websites|no.obj.|68GB|
|`streetart2023`|2023|Streetart|no.obj.|75GB|
|`eventUkraina2022`|2022-23|Russia's invasion of Ukraine|no.obj.|343GB|
|`valg2001`|2001|Political parties from the 2001 Parliamentary Election|no.obj.|1.6GB|
|`nettaviser`|2020-21|News websites|no.obj.|2.3TB|

----

[^1]: SolrWayback is open source and available through [GitHub](https://github.com/netarchivesuite/solrwayback/).