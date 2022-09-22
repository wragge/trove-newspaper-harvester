trove-newspaper-harvester
================

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

<div>

[![](https://zenodo.org/badge/DOI/10.5281/zenodo.7103174.svg)](https://doi.org/10.5281/zenodo.7103174)

</div>

[View the full
documentation](https://wragge.github.io/trove-newspaper-harvester/)

The Trove Newspaper (& Gazette) Harvester makes it easy to download
large quantities of digitised articles from [Trove’s newspapers and
gazettes](https://trove.nla.gov.au/newspaper/). Just give it a search
from the Trove web interface, and the harvester will save the metadata
of all the articles in a CSV (spreadsheet) file for further analysis.
You can also save the full text of every article, as well as copies of
the articles as JPG images, and even PDFs. While the web interface will
only show you the first 2,000 results matching your search, the
Newspaper Harvester will get everything.

## No installation required!

If you want to use the harvester without installing anything, just head
over to the [Trove Newspaper
Harvester](https://glam-workbench.github.io/trove-harvester/) section in
my GLAM Workbench.

## Installation

``` sh
pip install trove-newspaper-harvester
```

## Use as a library

``` python
from trove_newspaper_harvester.core import prepare_query, Harvester
```

Generate a set of query parameters using
[`prepare_query`](https://wragge.github.io/trove-newspaper-harvester/core.html#prepare_query).

``` python
my_query = "https://trove.nla.gov.au/search/category/newspapers?keyword=wragge"
my_api_key = "mYSecREtkEy"

my_query_params = prepare_query(query=my_query, key=my_api_key)
```

Initialise the
[`Harvester`](https://wragge.github.io/trove-newspaper-harvester/core.html#harvester)
with your query parameters.

``` sh
harvester = Harvester(query_params=my_query_params)
```

Start the harvest!

``` sh
harvester.harvest()
```

If the harvest fails just run
[`Harvester.harvest`](https://wragge.github.io/trove-newspaper-harvester/core.html#harvester.harvest)
again.

[See the core module
documentation](https://wragge.github.io/trove-newspaper-harvester/core.html)
for more options and examples.

## Use as a command-line tool

Before you do any harvesting you need to get yourself a [Trove API
key](https://trove.nla.gov.au/about/create-something/using-api).

There are three basic commands:

- **start** – start a new harvest
- **restart** – restart a stalled harvest
- **report** – view harvest details

### Start a harvest

To start a new harvest you can just do:

``` sh
troveharvester start "[Trove query]" [Trove API key]
```

The Trove query can either be a url copied and pasted from a search in
the [Trove web interface](http://trove.nla.gov.au/newspaper/), or a
Trove API query url constructed using something like the [Trove API
Console](https://troveconsole.herokuapp.com/). Enclose the url in double
quotes.

[See the CLI module
documentation](https://wragge.github.io/trove-newspaper-harvester/cli.html)
for more details.

------------------------------------------------------------------------

Created by [Tim Sherratt](https://timsherratt.org/) for the [GLAM
Workbench](https://glam-workbench.net/). Support this project by
becoming a [GitHub sponsor](https://github.com/sponsors/wragge?o=esb).
