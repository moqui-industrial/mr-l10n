# mr-l10n - Language Packs for MR Moqui

> **Not ready for production (before 0.1.0).** Like [MR Moqui](https://github.com/moqui/mr-moqui#readme), whose
> text these packs carry into other languages, this component is in early development. Screens and messages still
> change, so a pack can trail the English, and the data model changes without migrations. MR Moqui is for development
> machines only for now; the full notice is at the top of the [mr-moqui README](https://github.com/moqui/mr-moqui#readme).

Language packs for [MR Moqui](https://github.com/moqui/mr-moqui), the Moqui framework in Rust, and its applications:
the labels, field titles, messages, enumeration and status names, and email and print text, as data that loads into a
database.

| Language | Load type | Files |
|---|---|---|
| Spanish: neutral international Spanish, with a short overlay for Spain (`es_ES`) | `es` | `data/es/` |
| Simplified Chinese | `zh` | `data/zh/` |

## Coverage

| | Covered | Not yet |
|---|---|---|
| mr-moqui | framework, tools, webroot, basic-comms, example, dev-aide | |
| [mr-mantle](https://github.com/moqui/mr-mantle) | Enumerations and statuses, states and provinces, messages and templates | |
| [mr-marble](https://github.com/moqui/mr-marble) | Screens, email and print | |
| [mr-boss](https://github.com/moqui/mr-boss) | Commons, Comms, Projects, Products, Accounting, Warehouse, Manufacturing, Purchasing, Customer Service, and the shared screens they mount | Sales, Marketing, Commerce, Maintenance, People, Insights, Admin |
| [mr-pass](https://github.com/moqui/mr-pass) | | All of it |

Texts longer than 255 characters stay in English; they are listed in
[docs/Strings-Left-In-English.md](docs/Strings-Left-In-English.md).

## Loading a language

In an [mr-moqui](https://github.com/moqui/mr-moqui#quick-start) checkout, get the component with
`./moq component-get mr-l10n`. Each language's files have its code as their data type, so they load when that type
is loaded:

- **In development**, `./moq load` loads every type, and so does the first start of `./moq run` on an empty
  database. Both languages are there.
- **With the production conf or the binary alone**, `moqui load` and an empty-database start load `seed`,
  `seed-initial` and `install` only. Load Spanish with `moqui load types=es` and Simplified Chinese with
  `moqui load types=zh`, or add `es` or `zh` to a longer type list; `types=all` includes them.

A database that already has data does not pick a language up until that load runs. A person sees it when
their account's locale is that language.

## Adding a language

A new language is a directory `data/<code>/` whose files follow the Spanish key set, with the same names under the
new prefix and `type="<code>"`. The rules under [Writing rows](#writing-rows) apply, and the language gets a section
in [docs/Voice.md](docs/Voice.md) with its register, glossary and the words it avoids. A regional variant is a short
overlay file, as `EsRegional.xml` is for `es_ES`, not a second catalog.

## Files

Each language's files are in `data/<lang>/`, named by prefix (`Es` or `Zh`) and area, split into `A`, `B`, … parts when
large:

| Name | Contents |
| --- | --- |
| `Chrome*` | Shared labels and field titles |
| `Messages*`, `FrameworkExtra` | Service, screen and framework messages, including seed text added after the first catalog |
| `SeedEnum*`, `SeedMeasure`, `Geo` | Framework enumeration and status text, currency and unit descriptions, country names |
| `Tools*`, `Webroot`, `Example` | The tools screens, login and shell, the example app |
| `Comms*` | basic-comms: mail, chat and calls |
| `DevAide` | Dev AIDE |
| `Mantle*` | mr-mantle enumerations, states and provinces, messages and templates |
| `Marble*` | mr-marble screens, email and print |
| `Boss*` | mr-boss Commons, Comms, Projects, Products, Accounting, Warehouse, Manufacturing, Purchasing, and Customer Service, and the shared screens those apps mount |
| `EsRegional.xml` | `es_ES` overrides (still type `es`); `es_MX` has none of its own |

`Geo.geoName`, enumeration and status descriptions, status transition names, and UOM description and symbol have `enable-localization="true"`, so these rows show on screen. Product feature description and abbreviation do too. `geoNameLocal` is the place's own name, not the viewer's language. Party names, product names, and GL account names are stored text and stay as entered.

## Writing rows

The wording rules and glossaries for each language are in [docs/Voice.md](docs/Voice.md). In short: a row is stored
only when the text differs from the English original (the omitted originals are listed in `data/<lang>/unchanged-*.txt`,
which the loader ignores); placeholders (`${...}`, `{0}`, `{n,choice,...}`) and number patterns are copied unchanged;
and the localized value is at most 255 characters (`LocalizedMessage.original` holds at most 255 too). Longer texts
stay in English; they are listed in [docs/Strings-Left-In-English.md](docs/Strings-Left-In-English.md).

## License and Contributing

[CC0 1.0 Universal with a Grant of Patent License](LICENSE.md). To contribute code, sign
[AUTHORS.md](AUTHORS.md) in a commit from the account that submits the pull request; its Contributing
section has the details.
