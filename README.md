# PubTator-API-Wrapper
Functions to retrieve and process annotations with PubTator API

## Introduction

This is code that I wrote to help me use the PubMed and PubTator Central APIs.

My main use case for this "wrapper" was to take a single search term (e.g. "heart failure") and automatically create
a dataframe that contains each resulting PMID from PubMed, along with each Disease annotated in that PMID by PubTator Central,
plus that disease's corresponding MESH ID when available.

However! There are some basic functions in here that might be useful for other purposes. In general, it took a long time for me to
simply understand how to approach returning PMIDs and annotations from the PubMed and PTC databases, so I have outlined how to
do those things in the code and documentation. While this is neatly packaged up to serve my purposes well, I have tried to provide
thorough commenting in order to make these functions modular and modifiable to others' needs. There is a use case example included.

## Setup

All functions for the wrapper are contained in the file ['PTC Annotation Retrieval Functions'](https://github.com/pinglab-intern/PubTator-API-Wrapper/blob/master/PTC%20Annotation%20Retrieval%20Functions). Rename as needed.

This file contains no main function - individual functions must be accessed individually.

### Requirements

This wrapper requires:
* [BioPython](https://biopython.org/) (for the Entrez components)
* [pandas](https://pandas.pydata.org/)

## How to Use

[See Python usage example here.](https://github.com/pinglab-intern/PubTator-API-Wrapper/blob/master/Use_Example)

The wrapper may be used to retrieve a list of PMIDs from PubMed, then search PubTator Central for annotations of each. Output formats are one of 'XML', 'json', or 'PubTator', with the PubTator format returned as a table.

The following functions are available:
* search(query, search_place)
* get_annotations(a,b,query,aggregate, m_format, m_concept)
* aggregate_results(main_df)

## Credits
Script assembled by Marlee Zinsser while working with Harry Caufield in the Ping Lab at UCLA in Spring/Summer 2020.
