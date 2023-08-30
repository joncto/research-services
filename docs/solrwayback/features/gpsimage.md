---
title: GPS Image Search
layout: home
parent: SolrWayback
nav_order: 4
---

# GPS Image Search

The GPS Image Search allow you to make a geographical query for photographies. This applies for images with exif metadata, containing the geo-coordinates where it was captured. Far from all image files have this exif metadata included, but we still believe this approach provides an interesting perspective on the NWA collection.

The result view is limited to 500 results. To reduce the waiting time before results are returned, or receive more relevant results, you should limit your scope. This can be done geographically and by including a query.

## Table of content
1. [Define geographical scope](#define-geographical-scope)
2. [Include query](#include-query)
3. [Interact with results](#interact-with-results)
4. [List results without fetching images](#list-results-without-fetching-images)


## Define Geographical Scope
The easiest way to define the scope of a geographical image search is to zoom in/out and click on the location you want to search for.

You can also enter geo-coordinates for the location's latitude and longitude.

To widen or narrow your scope, adjust the size of the radius.

## Include query
You can limit your geo-based image search further by adding a query.

The default text `*:*` means that you are searching for any field in the index, with any value. In practice, you are searching through millions of images.

You can replace `*:*` with `collection:{collectionName}`. E.g. if you enter `collection:samisk`, the 
search will be limited to images from the Sámi collection. (See [LINK](.) for an overview of collections to scope by.)

## Interact with results
When the results are ready, thumbnails of the images will be displayed to the right.


## List results without fetching images
If you want to get an overview of the result, without having the images presented, you can do a service call with url parameters.

This is an example of a service call below, 

`http://localhost:8080/solrwayback/services/frontend/images/search/location/?query=*:*&latitude=60.3876&longitude=5.3182&d=50`

If you click on one of the links below the image, you will make a search and lose your image results. To explore the results without loosing it, right-click and choose "Open in new tab".

To view a larger version, simply click on the image you want to have a look at.

Below the thumbnail, you can click "Search for image" to make a query for that image. This is especially helpful if you want to see (???).

You can also choose "Pages linking to image" to make a query for web pages that uses this element

## Export
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.






----

