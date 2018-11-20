[![](https://img.shields.io/badge/OS-MacOS-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/pyversions/mac-localized.svg?longCache=True)](https://pypi.org/pypi/mac-localized/)
[![](https://img.shields.io/pypi/v/mac-localized.svg?maxAge=3600)](https://pypi.org/pypi/mac-localized/)
[![Travis](https://api.travis-ci.org/looking-for-a-job/mac-localized.py.svg?branch=master)](https://travis-ci.org/looking-for-a-job/mac-localized.py/)

#### Install
```bash
$ [sudo] pip install mac-localized
```

#### How it works
```
Release Notes.localized/
    .localized/
        en.strings
        de.strings
        ja.strings
```

`.strings`:
```
"Release Notes" = "Localized name";
```

#### Functions
function|description
-|-
`mac_localized.fullpath(path)`|return path with `.localized` postfix
`mac_localized.get(path, lang)`|return translation
`mac_localized.load(path)`|return dictionary with keys as languages and translations with values
`mac_localized.mkdir(path, **strings)`|mkdir (if not exists), write translations and return folder fullpath
`mac_localized.name(path)`|return folder name without `.localized` prefix
`mac_localized.rm(path, languages=None)`|rm .localized/ lang files or .localized/ folder
`mac_localized.update(path, **strings)`|update folder translations
`mac_localized.strings.find(path)`|return list with `.strings` files
`mac_localized.strings.load(path)`|return dictionary with keys as languages and translations with values

#### Examples
```python
>>> import mac_localized
>>> mac_localized.mkdir("folder",ru="ru translation",de="de translation")
'folder.localized'

>>> mac_localized.load("folder")
{'ru':'ru translation','de':'de translation'}

>>> mac_localized.update("folder",ru="new ru translation",de="new de translation")

>>> mac_localized.get("folder","ru")
'new ru translation'

>>> mac_localized.rm("folder",["ru"])
>>> mac_localized.rm("folder")  # rm all localizations
```

#### Links
+ [Localizing the Name of a Directory](https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemAdvancedPT/LocalizingtheNameofaDirectory/LocalizingtheNameofaDirectory.html)
+   [Display Names](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPFileSystem/Articles/DisplayNames.html)

<p align="center"><a href="https://pypi.org/project/readme-md/">readme-md</a> - README.md generator</p>