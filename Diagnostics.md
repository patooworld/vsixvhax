"Diagnostics" are what may be responsible for red or green squiggly lines you may have seen in your code while typing (note that the problem matcher when running a [build task](/vshaxe/vshaxe/wiki/Build-Tasks) can also add these, however).

[[images/diagnostics/invalid.png]]

Like errors during build tasks, Diagnostics are also shown in the Problems view:

[[images/diagnostics/problems.png]]

Diagnostics are incredibly useful since they are updated each time you save, and hence provide real-time feedback over whether your code is valid or not. This way, you can usually tell whether your code will compile, even before actually doing so.

>**Known issues:** simple syntax errors such as missing semicolons are currently not detected by diagnostics ([#102](https://github.com/vshaxe/vshaxe/issues/102)).

Since Diagnostics are updated on save, they combo very well with the `"files.autoSave": "afterDelay"` setting.

You can also run Diagnostics over all files in the current project by using the ["Run Global Diagnostics Check"](/vshaxe/vshaxe/wiki/Commands#haxe-run-global-diagnostics-check) command.

Diagnostics can not only inform you about invalid, but also unused code. One example for this are unused imports and usings:

[[images/diagnostics/unused-import.png]]

Another example are unused local variables and expressions whose values are not used for anything:

[[images/diagnostics/no-effect.png]]