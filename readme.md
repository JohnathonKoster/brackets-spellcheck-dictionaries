# Linguistics Dictionary

The Linguistics Dictionary extension contains the dictionaries required for the main Adobe Brackets spell checker  extension (which can be found at https://github.com/JohnathonKoster/brackets-spellcheck). The extension is separated into various different parts, based on how each part is expected to be used; there are four main directories to the Dictionary extension:

* `natural-languages` - This directory is used to store natural language dictionaries. For example, this directory would contain an English dictionary, and any variations or dialects.
* `generic-utilities` - This directory is used to store specific lists and dictionaries. Things like common file extensions and terms can be found in this directory.
* `user-profiles` - This directory contains user-defined language profiles that can be loaded into the spell checking system. For example, you can create a profile that loads a natural language as well as dictionary of medical terms without much hassle.
* `programming-languages` - This directory contains many useful things for developers, and is covered in greater detail in another section.

## Natural Languages

Natural languages (such as Spanish or English) are stored in the `natural-languages` directory. Each language must be stored within its own subdirectory. Each directory must contain at least a dictionary file and a `language.json` file, however, it is highly recommended that all natural languages also supply an affix file.

The following is an example directory structure for the `en_US` locale:

```
natural-languages
    en_US
        en_US.aff
        en_US.dic
        language.json
```

It should be noted that the directory name and the names of the dictionary and affix files must be the same (in the above example they all have the name `en_US`). This helps to keep the loader simpler because it can make a few assumptions about the structure of the `natural-languages` directory.

### `language.json`

The `language.json` file is very simple. Here is an example file that can be used for the `en_US` locale:

```json
{
    "locale": "en_US",
    "name": "English (United States)",
    "description": "The default dictionary for the English (United States).",
    "version": "1.0.0",
    "author": "",
    "url": "",
    "releaseDate": ""
}
```

It is recommended that all fields have some value, but only the `locale` and the `name` are absolutely required to have values. Even though the other values do not have to be entered, at least ensure that the key/value pairs are present in your `language.json` file.

The `locale` property of the `language.json` file must also match the name of the directory, affix and dictionary paths (in the above example, the `locale` is set to `en_US`, which is the same as the directory and file names).

### Naming Language Directory and Files

Linguistics does not impose any one standard for how to determine the names of language files and directories.

## Sourcing Dictionaries and Affix Files

Most of the natural languages included in the Dictionary extension are source from the [titoBouzout/Dictinoaries](https://github.com/titoBouzout/Dictionaries) GitHub repository. This repository contains many dictionaries that are compatible with Sublime Text. Dictionaries from this repository can be identified if a text file exists within the dictionary's directory (usually with the same name as the dictionary directory).
