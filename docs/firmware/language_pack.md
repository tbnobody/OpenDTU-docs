# Language Packs

!!! note "Available language packs"
    Ready-to-use language packs can be found [in the code
    repository](https://github.com/tbnobody/OpenDTU/tree/master/lang){target=_blank}.

## Summary

Language packs currently contain the translations for the web interface and
the display.
Additional translations for e.g. the event log will follow.

## Installation / Upload of language packs

Language packs can be uploaded to the device using the [Config Management](configuration/config_settings.md) function.
Select "Language Pack" in the restore section, select a .json file containing your
language and press "Restore".
Afterwards all language selection drop down menues contain the new language.

## File structure

### Meta data

The language pack contains a `meta` section with the following parameters:

* `name`: Human readable name of the language. Will be used in the frontend (Should be in the appropriate language)
* `code`: Set 1 ISO[^1] code of the language

### Display data

The `display` section contains all the translation keys used for externally connected displays. The following parameters are used:

* `date_format`: "%d/%m/%Y %H:%M",
* `offline`: Text if the invters are offline,
* `power_w`: Text for current power in W. A float gets injected and can be formatted[^2] (e.g. `%.0f`)
* `power_kw`: Text for current power in W. A float gets injected and can be formatted[^2] (e.g. `%.1f`)
* `yield_today_wh`: Text for daily production in Wh. A float gets injected and can be formatted[^2] (e.g. `%4.0f`)
* `yield_today_kwh`: Text for daily production in kWh. A float gets injected and can be formatted[^2] (e.g. `%.1f`)
* `yield_total_kwh`: Text for total production in kWh and one decimal places. A float gets injected and can be formatted[^2] (e.g. `%.1f`)
* `yield_total_mwh`: Text for total production in kWh and zero decimal places. A float gets injected and can be formatted[^2] (e.g. `%.0f`)

### WebApp data

The `webapp` section contains all the translation keys as used in the web app.

### Example

```json
{
    "meta": {
        "name": "Italiano",
        "code": "it"
    },
    "display": {
        "date_format": "%d/%m/%Y %H:%M",
        ...
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
[^2]: [Printf format specifier](https://en.wikipedia.org/wiki/Printf#Format_specifier){target=_blank}
