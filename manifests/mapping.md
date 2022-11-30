# High-level overview

1. Metadata about the IIIF resource (`context`, `id`, `type`, `label`)
2. Summary (`summary`)
3. Descriptive Metadata about the object
4. Rights Information (`rights`, `requiredStatement`)[^1]
5. Related links (`logo`,`homepage`, `seeAlso`, `provider`)
6. Presentation information (`viewing Direction`, `thumbnail`)
7. List of Canvases (`items`, `id`, `type`, `label`), mostly pointing to a IIIF Image API service

## Mapping Description

### Metadata about the IIIF resource

| **Property** | **Content** |
|--------------|-------------|
| `@context`   |     It has to be  "http://iiif.io/api/presentation/3/context.json"       |
| `id`         |             |
| `type`       |             |
| `label`      |             |

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