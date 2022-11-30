# High-level overview

1. Metadata about the IIIF resource (`context`, `id`, `type`, `label`)
2. Summary (`summary`)
3. Descriptive Metadata about the object
4. Rights Information (`rights`, `requiredStatement`)
5. Related links (`logo`,`homepage`, `seeAlso`, `provider`)
6. Presentation information (`viewing Direction`, `thumbnail`)
7. List of Canvases (`items`, `id`, `type`, `label`), mostly pointing to a IIIF Image API service

## Mapping Description

Here is a mapping description following the structure (in which order the properties or set of properties appear) of the Manifests created in this repository. It should be noted that IIIF has a different kind of classification, which is: 

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

### Descriptive Metadata about the object

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