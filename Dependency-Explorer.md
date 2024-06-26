The Haxe extension adds a "Haxe Dependencies" tree view to the explorer. It contains all Haxelibs and classpaths from the currently selected [Configuration](https://github.com/vshaxe/vshaxe/wiki/Configuration#configurations-and-display-server), as well as the Haxe Standard Library. Classpaths that are part of the current workspace are ignored to avoid duplicating what the regular File Explorer already displays.

![](images/dependency-explorer/tree-view.gif)

The ability to browse through the files of a Haxelib is particularly useful for Haxelib authors or contributors.

> **Note:** if you want to navigate to a particular type in a dependency, using [Workspace Symbols](https://github.com/vshaxe/vshaxe/wiki/Workspace-Symbols) is usually quicker / more convenient.

Just like the regular explorer view, "Haxe Dependencies" also supports the `"explorer.autoReveal"` setting (enabled by default). So whenever you open a file of a dependency (via workspace symbols, drag-and-dropping the file into VSCode...), the view automatically reveals and selects that file.