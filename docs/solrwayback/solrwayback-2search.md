---
title: Search synthax
layout: home
parent: SolrWayback
nav_order: 2
---

# Search synthax

SolrWayback have advanced features for search. Understanding its synthax will allow you to produce refined and well-scoped search results, which can also be used to define a corpus of content for further examination. 

## Table of content
1. [Boolean operators](#boolean-operators)
2. [Parentheses for mixing operators](#parentheses-for-mixing-operators)
3. [Using fields](#using-fields)
4. [Search phrases with quotation marks](#search-phrases-with-quotation-marks)
5. [Wildcards](#wildcards)
6. [Range search](#range-search)
7. [Default fields](#range-search)
8. [Field desriptions](#field-desriptions)

## Boolean operators
The boolean operators **AND**, **OR** and **NOT** are supported. They MUST be entered in uppercase, if not they will be considered as regular search words. 

[//]: # (HTML table with examples and description of operators)

<table border='1'>
<tr>
<td><b>Operator</b></td>
<td><b>Example </td>
<td><b>Description </td>
</tr>
<tr>
 <td>AND</td>
 <td>Støre AND Ukraina</td>
 <td>Both terms must match. <br> Same as: Støre Ukraina <br>AND is the default operator between terms if not specified</td>
</tr>
<tr>
 <td>OR</td>
 <td>computer OR apple</td>
 <td>Any of the terms can match</td>
</tr>
<tr>
 <td>NOT</td>
 <td>Støre NOT Ukraina</td>
 <td>Return matches on 'Støre' that does not include 'Ukraina'.<br> Alternative syntax: computer -apple</td>
</tr>
</table>

## Parentheses for mixing operators
If you mix several different operators, you should use parentheses () to avoid ambiguous interpretation.<br>
Example: <b>(Støre AND Ukraina) OR (Huitfeldt)</b><br> 
This will return results if either 'Støre AND Ukraina' or 'Huitfeldt' is found.

## Using fields
You can refine your search considerably if you scope your query with fields. For a complete list of fields in the index, see [LINK](.)

Here are some examples of how you can use fields to limit your query:
- `domain:regjeringen.no AND Støre AND Ukraina`<br>
*resources from regjeringen.no, containing both 'Støre' and 'Ukraina'*

- `content_language:no AND makeup`<br>
*content classified as Norwegian language, containing the word 'makeup'*

- `content_type_norm:image`<br>
*resources classified as images*

- `collection:streetart2023 AND content_type_norm:image`<br>
*resources from the 'streetart2023' collection, classified as images*

## Search phrases with quotation marks
To search for phrases, simply put your search words within quotation marks.

- `"Støre og Zelenskyj"` will only return results where the words are next to each other.

You can also use the tilde character `~` to return hits with words appearing close to eachother.

- `"Støre Zelenskyj"~4` allows for up to 4 other words in between your search words.

Phrase search is also important when the text you are searching for contains special characters, like urls with `/`.
- links:"http://mittdomene.no/minside.html" will search for all resources containing links to that url.

## Wildcards
The search engine support the use of wildcard characters.

Asterisk (`*`) is used for trucation. E.g.
- `Universitets*` will return results for all words that starts with this, such as "universitetsbiblioteket" and "universitetslektor"

Question mark (`?`) is used as a joker character. This can be useful for words with variations in spelling. E.g.
- `Zelensk??` will return results for both "Zelenskij", "Zelenskyj" and "Zelenskyy".

**WARNING!** Do not use wildcards in the start of words (prefix). This often take too long time to resolve, and result in a timeout. 

## Range search
If you are search for a field where the value is numeric or a timestamp, you can specify a range of values to search for. E.g.:
- `content_type_norm:image AND content_length:[1000000 TO 10000000]` will search for images of size between 1-10Mb
- `crawl_date:[2022-12-01T00:00:00Z TO 2023-01-01T00:00:00Z]` will search for resources archived in January 2010.<br>
*(For more info about timestamps, see [LINK](.))*

## Default fields
When you search without a field prefix, you will only search in some default search fields.

These are the typical fields for text search, like `content_text`, `title`, `url` etc.

The default search fields are case insensitive. For some other fields, case must match. <br>

You should always use field prefix search if you want to search a non-default search field. E.g.
- `content_type_served:"image/jpeg"`


## Field desriptions
Below you will find explanations of the most crucial fields. From the search result, you can also click "See all fields" for a resource to inspect other possible fields.


<table border='1'>
<tr>
    <td><b>Field</b></td> 
    <td><b>Multivalued</b></td> 
    <td><b>Type</b></td> 
    <td><b>Description</b></td>
</tr>

<tr>
    <td>id</td>
    <td>no</td>
    <td>string</td>
    <td>Unique identifier for each document.</td>
</tr>

<tr>
    <td>index_time</td>
    <td>no</td>
    <td>date</td>
    <td>When was the warc-file indexed</td>
</tr>

<tr>
    <td>author</td>
    <td>yes</td>
    <td>string</td>
    <td>From Author meta-data (word,html,pdf,image etc.)</td>
</tr>

<tr>
    <td>description</td>
    <td>no</td>
    <td>string</td>
    <td>From description meta-data (word,html,pdf,image etc.)</td>
</tr>

<tr>
    <td>title</td>
    <td>no</td>
    <td>string</td>
    <td>From title meta-data</td>
</tr>

<tr>
    <td>content_language</td>
    <td>no</td>
    <td>string</td>
    <td>Language of text (from Tika)</td>
</tr>

<tr>
    <td>content_length</td>
    <td>no</td>
    <td>int</td>
    <td>Content length of the payload from the server </td>
</tr>

<tr>
    <td>content_text_length</td>
    <td>no</td>
    <td>int</td>
    <td>Content length of the extracted text</td>
</tr>

<tr>
    <td>content_type_norm</td>
    <td>no</td>
    <td>string</td>
    <td>Content type determined by Tika. Possible values: html,image,pdf,audio,video,word,powerpoint,excel,text,other</td>
</tr>

<tr>
    <td>type</td>
    <td>no</td>
    <td>string</td>
    <td>Almost same content_type_norm. Just more human names and fewer values: Web Page, Image, Other, Document, Audio, Video, Presentation, Data</td>
</tr>

<tr>
    <td>hash</td>
    <td>no</td>
    <td>string</td>
    <td>A hash value of the payload. Identical payload will have identical hash</td>
</tr>

<tr>
    <td>crawl_date</td>
    <td>no</td>
    <td>date</td>
    <td>When was then url crawled. Additional similar fields: crawl_year_month_day,crawl_year_month,crawl_year</td>
</tr>

<tr>
    <td>url</td>
    <td>no</td>
    <td>string</td>
    <td>The exact url seen from the harvest client that created the warc-file</td>
</tr>

<tr>
    <td>url_norm</td>
    <td>no</td>
    <td>string</td>
    <td>A normalized version of the url field. It is lowercased and https is made into http. Also finds unique representation of varius encodings. Also removes som predefined parameter names such as session-id etc. This field is very important for playback in SolrWayback.</td>
</tr>

<tr>
    <td>domain</td>
    <td>no</td>
    <td>string</td>
    <td>Domain of the URL. Example: nb.dk</td>
</tr>

<tr>
    <td>host</td>
    <td>no</td>
    <td>string</td>
    <td>Host of the URL, this includes subdomain Example: nettarkivet.nb.no</td>
</tr>

<tr>
    <td>public_suffix</td>
    <td>no</td>
    <td>string</td>
    <td>
    The public suffix of the url: Example: no, org, co.uk</td>
</tr>

<tr>
    <td>resourcename</td>
    <td>no</td>
    <td>string</td>
    <td>Last part of the URL after '/' with query parameters. E.g. index.html or cats.jpg&size=100</td>
</tr>

<tr>
    <td>image_size</td>
    <td>no</td>
    <td>long</td>
    <td>The size of the image in pixels. There are also similar fields image_height and image_width</td>
</tr>

<tr>
    <td>links_images</td>
    <td>yes</td>
    <td>string</td>
    <td> The links of all images tags on a HTML page.</td>
</tr>

<tr>
    <td>links</td>
    <td>yes</td>
    <td>string</td>
    <td> The links of all  'a href' tags on an HTML page. Similar fields: links_domains,links_hosts</td>
</tr>

<tr>
    <td>links_norm</td>
    <td>yes</td>
    <td>string</td>
    <td>Same as the links field except values are normalized</td>
</tr>

<tr>
    <td>server</td>
    <td>yes</td>
    <td>string</td>
    <td>Value of the Server field in the HTTP header</td>
</tr>

<tr>
    <td>statuscode</td>
    <td>no</td>
    <td>int</td>
    <td>The http status code in the HTTP header. </td>
</tr>

<tr>
    <td>warc_ip</td>
    <td>no</td>
    <td>string</td>
    <td>IP-address of the server. Taken from the metadat field WARC-IP-Address in the warc-header. </td>
</tr>

<tr>
    <td>source_file_path</td>
    <td>no</td>
    <td>string</td>
    <td>Full path to the warc-file where the resource is from. The field source_file_offset gives the offset for the resource in that warc-file</td>
</tr>


<tr>
    <td>source_file</td>
    <td>no</td>
    <td>string</td>
    <td>The filename of the WARC-file without the absolute file path. Is case sensitive</td>
</tr>

</table>

----

