# SAPA-IIIF
This repository contains IIIF Resource Templates for the Swiss Archive of the Performing Arts (SAPA). 

## Structure

It contains the following: 

- [3 Manifest Templates](/manifests/) (IIIF Presentation API 3.0)
- [1 Collection Template](/collections/) (IIIF Presentation API 3.0)
- [Activity Streams for the above IIIF resources](/activity/) (IIIF Change Discovery API 1.0)

Temporarily, the following [IIIF Manifest](https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1553-FO-86-1.json) from the Fonds Erismann has been created.

## Modelling

The templates have been created on the basis of the following portraits, all available via the [SAPA Metaphacts instance](https://www.performing-arts.ch/) and the images being served by [Cantaloupe](https://media.performing-arts.ch/iiif/3):

- http://data.performing-arts.ch/r/d1534a8c-f0b3-466a-9024-1d59f67a2e5b
- http://data.performing-arts.ch/r/c85a5ebd-945d-4629-8b21-49af3eacda9b
- http://data.performing-arts.ch/r/70001858-59c9-4d0b-b459-d6e9c88de01d

### Manifest

1. Metadata about the IIIF resource (`context`, `id`, `type`, `label`)
2. Summary (`summary`)
3. Descriptive Metadata about the object
4. Rights Information (`rights`, `requiredStatement`)
5. Related links (`logo`,`homepage`, `seeAlso`, `provider`)
6. Presentation information (`viewingDirection`, `thumbnail`)
7. List of Canvases (`items`, `id`, `type`, `label`), mostly pointing to a IIIF Image API service

Further mapping explanation is done [here](manifests/mapping.md).

### Collection

1. Metadata about the IIIF resource (`context`, `id`, `type`, `label`)
2. Summary (`summary`)
3. Related links (`logo`, `provider`)
4. List of Manifests/Collections (`items`, `id`, `type`, `label` for each resource)

### Activity Streams

Based on the [IIIF Change Discovery  API endpoint from the Bodleian Libraries](https://iiif.bodleian.ox.ac.uk/iiif/activity/all-changes), the following templates were created: 
- an `OrderedCollection` ([all-changes](activity/all-changes.json))
- a first `OrderedCollectionPage` ([page-0](activity/page-0.json))
- the subsequent pages pointing to each of the IIIF Manifests which are all `Create` activities and can be found in this [directory](activity/create/).