<!--
https://readme42.com
-->


[![](https://img.shields.io/pypi/v/mac-localized.svg?maxAge=3600)](https://pypi.org/project/mac-localized/)
[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/mac-localized.py/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/mac-localized.py/actions)

### Installation
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

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>
