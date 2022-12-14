# Mapping

- [High-level overview](#high-level-overview)
- [Mapping Description](#mapping-description)
    - [Metadata about the IIIF resource](#metadata-about-the-iiif-resource)
    - [Summary](#summary)
    - [Descriptive Metadata](#descriptive-metadata)
    - [Rights Information](#rights-information)
    - [Related links](#related-links) 
    - [Presentation information](#presentation-information)
    - [List of Canvases](#list-of-canvases)

## High-level overview

1. Metadata about the IIIF resource (`context`, `id`, `type`, `label`)
2. Summary (`summary`)
3. Descriptive Metadata about the object
4. Rights Information (`rights`, `requiredStatement`)
5. Related links (`logo`,`homepage`, `seeAlso`, `provider`)
6. Presentation information (`viewingDirection`, `thumbnail`)
7. List of Canvases (`items`, `id`, `type`, `label`), mostly pointing to a IIIF Image API service

## Mapping Description

Hereafter is a mapping description following the structure, i.e. in which order the properties or set of properties appear, of the Manifests created in this repository. It should be noted that the [IIIF Presentation API 3.0](https://iiif.io/api/presentation/3.0/#3-resource-properties) has a different kind of classification for properties, which is: 

- Descriptive Properties
- Technical Properties
- Linking Properties
- Structural Properties

### Metadata about the IIIF resource

| **Property** | **Content** |
|--------------|-------------|
| `@context`   |     It has to point to the IIIF Presentation API  `"http://iiif.io/api/presentation/3/context.json"`       |
| `id`         |      URL of the Manifest       |
| `type`       |      `"Manifest"`       |
| `label`      |        It can basically be anything, but it is recommended to have something short and textual that can be easily understood by humans. It can be mapped in several languages.     |

```
    "@context": "http://iiif.io/api/presentation/3/context.json",
    "id": "https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1027-6-10-25-2.json",
    "type": "Manifest",
    "label": {
      "en": [
        "Portrait of Jan Veen"
      ],
      "de": [
        "Portrait von Jan Veen"
      ],
      "fr": [
        "Portrait de Jan Veen"
      ],
      "it":[
        "Ritratto fotografico di Jan Veen"
      ]
    }
```

### Summary

| **Property** | **Content** |
|--------------|-------------|
| `summary`    |       A short textual summary intended to be conveyed to the user when the metadata entries for the resource are not being displayed      |

```
    "summary": {
      "en": [
        "IIIF Manifest of the portrait of Jan Veen"
      ]
    },
```

### Descriptive Metadata

| **Property** | **Content** |
|--------------|-------------|
| `metadata`    |       An ordered list of `label` and `values` entries that can be mapped in different languages. The content is not intended to convey semantics, its only goal is to provide some information for presentation.   |

```
    "metadata": [
      {
        "label": {
          "en": [
            "Name"
          ],
          "de":[
            "Name"
          ],
          "fr":[
            "Nom"
          ],
          "it":[
            "Nome"
          ]
        },
        "value": {
          "en": [
            "Jan Veen"
          ],
          "de":[
            "Jan Veen"
          ],
          "fr":[
            "Jan Veen"
          ],
          "it":[
            "Jan Veen"
          ]
        }
      },
```

### Rights Information

| **Property** | **Content** |
|--------------|-------------|
| `rights`    |      It can be either a string or a URI when the value is drawn from Creative Commons or RightsStatements.org     |
| `requiredStatement`    |   A copyright statement, the name of the organization can be mentioned          |

```
    "rights": "http://creativecommons.org/licenses/by-sa/4.0/",
    "requiredStatement": {
      "label": {
        "en": [
          "Copyright"
        ]
      },
      "value": {
        "en": [
          "All rights reserved to the SAPA Foundation"
        ]
      }
    },
```

### Related links

| **Property** | **Content** |
|--------------|-------------|
| `logo`       |       link to the logo of the organization, can also point to a IIIF Image API service, must be put at the provider level (unfortunately, it isn't yet displayed on Mirador due to a bug - cf. https://github.com/IIIF-Commons/manifesto/pull/111/files )      |
| `homepage`   |   On the Manifest level, homepage of the object, on the provider level, homepage of the organization/person reponsible for this object          |
| `seeAlso`    |     Pointers to structured metadata, could be used for aggregation purposes        |
| `provider`   |      information about the organization, could be used for aggregation purposes       |

```
    "homepage": [
      {
        "id": "https://sapa.swiss/example",
        "type": "Text",
        "label": {
          "en": [
            "Example SAPA Homepage"
          ]
        },
        "format": "text/html"
      }
    ],
    "seeAlso": [
      {
        "id": "http://data.performing-arts.ch/r/70001858-59c9-4d0b-b459-d6e9c88de01d",
        "type": "Text",
        "label": {
          "en": [
            "Record of Jan Veen on Metaphacts"
          ]
        },
        "format": "text/html"
      }
    ],
    "provider": [
      {
        "id": "https://d-nb.info/gnd/1150311754",
        "type": "Agent",
        "label": {
          "en": [
            "SAPA, Swiss Archive of the Performing Arts"
          ],
          "de": [
            "Stiftung SAPA, Schweizer Archiv der Darstellenden K??nste"
          ],
          "fr": [
            "Fondation SAPA, Archives suisses des arts de la sc??ne"
          ],
          "it": [
            "Fondazione SAPA, Archivio svizzero delle arti della scena"
          ]
        },
        "homepage": [
          {
            "id": "https://sapa.swiss/",
            "type": "Text",
            "label": {
              "en": [
                "The SAPA Foundation, Swiss Archive of the Performing Arts, collects documents and objects of importance to the history of the performing arts and makes them accessible to a wider audience."
              ],
              "de": [
                "Die Stiftung SAPA, Schweizer Archiv der Darstellenden K??nste, sammelt Dokumente und Objekte, die f??r die Geschichte der Darstellenden K??nste bedeutsam sind, und stellt diese einem breiten Publikum zur Verf??gung."
              ],
              "fr": [
                "La Fondation SAPA, Archives suisses des arts de la sc??ne, collecte et met ?? disposition de tous les publics les documents et objets constituant l???histoire des arts de la sc??ne en Suisse. Sa mission: pr??server les traces de ces arts ??ph??m??res et complexes pour les transmettre aux g??n??rations futures."
              ],
              "it": [
                "SAPA raccoglie e mette a disposizione del pubblico documenti e oggetti di rilevanza storica per le arti sceniche in Svizzera. La Fondazione si pone l???obiettivo di preservare le tracce di queste arti effimere e complesse per tramandarle alle generazioni future."
              ]
            },
            "format": "text/html"
          }
        ],
        "logo": [
          {
            "id": "https://memobase.ch/sites/default/files/2021-05/sap-logo.jpg",
            "type": "Image",
            "format": "image/jpeg",
            "height": 100,
            "width": 260
          }
        ]
      }
    ],
```

### Presentation information

| **Property** | **Content** |
|--------------|-------------|
| `viewingDirection`        |    this property is not mandatory but it should be included, by default viewers should displayed objects [from left to right](https://iiif.io/api/presentation/3.0/#viewingdirection).        |
| `thumbnail`               |        it is usually the content that is painted onto the first Canvas, a IIIF Image API can be leveraged through the `service` pattern   |

```
        "thumbnail": [
          {
            "id": "https://media.performing-arts.ch/iiif/3/image%2F1027-6-10-25-2/full/80,/0/default.jpg",
            "type": "Image",
            "format": "image/jpeg",
            "service": [
              {
                "id": "https://media.performing-arts.ch/iiif/3/image%2F1027-6-10-25-2",
                "type": "ImageService3",
                "profile": "level2"
              }
            ]
          }
        ],
    "viewingDirection": "left-to-right",
```

### List of Canvases 

_The `Canvas` represents an individual page or view and acts as a central point for assembling the different content resources that make up the display._

| **Property** | **Content** |
|--------------|-------------|
| `items`      |       a list of all Canvases      |
| `id`         |      URIs of each Canvas, they are usually not dereferenced but they must be unique.       |
| `type`       |        `"Canvas"`     |
| `label`      |       label of the Canvas, can be the identifier or just an incremental number (page, folio)      |

What needs to be specified then: 
- Area of the Canvas in terms of `height`and `width` and/or `duration`. Usually, they have the same pixel values as the images and/or the duration of the audio file in seconds.
- For images, the format and a related IIIF Image Service

```
    "items": [
      {
        "id": "https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1027-6-10-25-2/canvas/p1",
        "type": "Canvas",
        "label": {
        "none": [
          "1027-6-10-25-2"
        ]
      },
        "height": 850,
        "width": 799,
        "items": [
          {
            "id": "https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1027-6-10-25-2/canvas/p1/1",
            "type": "AnnotationPage",
            "items": [
              {
                "id": "https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1027-6-10-25-2/p0001-image",
                "type": "Annotation",
                "motivation": "painting",
                "body": {
                  "id": "https://media.performing-arts.ch/iiif/3/image%2F1027-6-10-25-2/full/max/0/default.jpg",
                  "type": "Image",
                  "format": "image/jpeg",
                  "height": 850,
                  "width": 799,
                  "service": [
                    {
                      "id": "https://media.performing-arts.ch/iiif/3/image%2F1027-6-10-25-2/",
                      "type": "ImageService3",
                      "profile": "level2"
                    }
                  ]
                },
                "target": "https://raw.githubusercontent.com/julsraemy/SAPA-IIIF/main/manifests/1027-6-10-25-2/canvas/p1/1"
              }
            ]
          }
        ]
      }
    ]
  }
```