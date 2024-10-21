# Language Packs

!!! note "Available language packs"
    Ready-to-use language packs can be found [in the code
    repository](https://github.com/tbnobody/OpenDTU/lang){target=_blank}.

## Summary

Language packs currently contain the translations for the web interface.
Additional translations for e.g. the display will follow.

## File structure

### Meta data

The language pack contains a `meta` section with the following parameters:

* `name`: Human readable name of the language. Will be used in the frontend (Should be in the appropriate language)
* `code`: Set 1 ISO[^1] code of the language

### WebApp data

The `webapp` section contains all the translation keys as used in the web app.

### Example

```json
{
    "meta": {
        "name": "Italiano",
        "code": "it"
    },
    "webapp": {
        "menu": {
            ...
        },
        ...
    }
}
```

[^1]: [ISO 639 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes){target=_blank}
