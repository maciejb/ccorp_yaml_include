# CCorp Ruamel.YAML Include Extension

This package extends Ruamel.YAML (a fork of PyYaml) to implement the `!include` tag in the _composer_, which allows the use of YAML anchors across included files. The prior way of achiving this required modifying the structure of files to invert the inclusion of files, and modifying the loading of the included file to patch in the anchors parsed thusfar. Unfortunately, this isn't possible on an existing collection of YAML files without a _lot_ of pushback from other developers, and therefore this package was developed. It processes `!include` tags as they are encountered by the composer rather than generating a tagged scalar to be processed by the constructor, allowing the processing to happen as a C/C++ programmer would expect, rather than defering until after composition.
