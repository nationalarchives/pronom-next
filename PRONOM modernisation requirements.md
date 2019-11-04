# PRONOM – modernisation of data infrastructure and service

## Background
PRONOM is a technical registry of file formats which is created, maintained and managed by The National Archives. PRONOM contains information about a wide range of file formats and includes descriptions, extensions, media types, and file format identification signatures.

The PRONOM service is used by archives, libraries and other memory and learning institutions around the globe, many of which contribute data to the service. 
The service includes two key elements:
-	File format signatures

A file format signature is a pattern, unique to a particular file format (or version of a file format) which enables digital objects to be characterised and identified. This identification is essential to the long-term preservation of digital records.

-	The PRONOM service
The service offers regular releases of the file format signatures. These are available for download via a web service. Additional tools to assist in researching and creating new signatures are also available.

Various tools and services use the PRONOM signatures to carry out file format identification. The most widely use of these is DROID. This is also developed and maintained by The National Archives.

## Requirements
### 1.	Modernise the data infrastructure
The live PRONOM service currently relies on a Microsoft SQL Server database.  Data is added or updated using a legacy Microsoft Access database and an Access Data Project (ADP) file. Since Access 2010 reaches end of support in October 2020, it is necessary to modernise this infrastructure. This offers an opportunity to consider alternatives to the relational data model, and it is anticipated that a graph data approach will lend itself well to these requirements. The following are critical requirements:

a)	The continuing ability to generate DROID-compatible signature files available to download via the PRONOM web service. The current DROID signature file schema is available here: http://www.nationalarchives.gov.uk/aboutapps/fileformat/pdf/automatic_format_identification.pdf

b)	The ability to make this data available via the PRONOM web service in a range of data formats, under the existing addressing scheme (e.g. http://nationalarchives.gov.uk/pronom/fmt/111)

c)	The ability for digital archivists to add or edit data in a simple, forms-based manner, without any need to understand or learn any querying language

### 2.	Refine the data model
The data model makes provision for various types of information that has never been captured. For example, it was originally envisioned that the service would capture information about file format obsolescence risk. This data has never been populated.
There are additional limitations. For example, we can only associate a single contributor with a particular file format entry. In reality, an entry may have multiple contributors. 
We wish to rationalise and refine the data model, without the loss of substantive data from the system.

### 3.	Extend the PRONOM signature vocabulary
The current PRONOM signature vocabulary has a number of limitations that prevent the expression of certain patterns. For example, the patterns necessary to describe container formats cannot currently be expressed via PRONOM. These additional requirements are being captured on GitHub - https://github.com/digital-preservation/pronom/issues

### 4.	Facilitate better linking and sharing of data and resources
We wish to create links, in both directions, between PRONOM and a number of external data sources. Known sources include the Library of Congress file format registry, Wikidata, and the nascent Preservation Action Registry.
Facilitating this linking may include providing an API or endpoint for PRONOM that other sources can query. The solution should facilitate specific links, and be flexible enough to allow arbitrary linking in the future as further data sources become available or known.
