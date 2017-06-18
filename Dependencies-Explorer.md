The Haxe extension adds a "Haxe Dependencies" tree view to the explorer. It contains the Haxelibs and Classpaths from the currently selected [Display Configuration](https://github.com/vshaxe/vshaxe/wiki/Configuration#display-configurations-and-display-server), as well as the Haxe Standard Library. Classpaths that are part of the current workspace are ignored to avoid duplicating what the explorer already displays.

[[images/dependencies-explorer/tree-view.png]]

The ability to browse through the files of a Haxelib is particularly useful for Haxelib authors or contributors.

Hint: if you want to navigate to a particular type in a dependency, using [Workspace Symbols](https://github.com/vshaxe/vshaxe/wiki/Workspace-Symbols) is usually quicker / more convenient.