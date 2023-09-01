---
title: Facets
layout: home
parent: Search
grand_parent: Solrwayback
nav_order: 3
permalink: /docs/solrwayback/search/facets
---

# Facets

SolrWayback have some different modes for search:

- [Text search](#text-search) (default)
- [Grouped search](#grouped-search)
- [Image search](#image-search)
- [Url search](#url-search)
- [Search with uploaded file](#search-with-uploaded-file)

## Text search
This is the default mode. For more information, see [Search synthax](./search-synthax.md) and [Field descriptions](./fields.md).

## Grouped search
This mode will group the results by URL. If several hits have the same URL (different versions of a document), only the most recent version will be presented in your result.

## Image search
In principle, this mode allow image search in the context of text.

The result will show images that appear in HTML pages, close to your search word/phrase.

## URL search
Search for a specific URL. This search encodes the domain name and normalise the URL, finding all different representations of the URL.

## Search with uploaded file
*We are sorry, but this feature is currently unstable.*



