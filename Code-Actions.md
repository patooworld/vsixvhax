When a Code Action is available for the current selection / cursor position, this is indicated by a light bulb to the left of the editor:

[[images/code-actions/light-bulb.png]]

To show the available actions, either click the light bulb or press <kbd>Ctrl</kbd>+<kbd>.</kbd>. This will open a popup menu:

[[images/code-actions/popup.png]]

In case you want to change the default shortcut, the `command` for this keybinding is `"editor.action.quickFix"`.

In the following sections, we will showcase all Code Actions that are associated with [Diagnostics](/vshaxe/vshaxe/wiki/Diagnostics). There are also some Code Actions for [Code Generation](/vshaxe/vshaxe/wiki/Code-Generation), please refer to that page for details on those.

### Import actions

There are some code actions to deal with importing unknown identifiers. A proper "auto-import" (adding an import automatically when a type is selected from the completion list) is still planned, however, as this is not a perfect replacement for it (see [#2](/vshaxe/vshaxe/issues/2)).

>**Known issues:**
> - An import suggestion can only appear for types that are being compiled ([#96](https://github.com/vshaxe/vshaxe/issues/96)). If the compiler never comes across a particular type (if it is not imported from anywhere), it cannot be suggested.
> - Import suggestions are currently not triggered in some places, for instance in class fields ([haxe#5950](https://github.com/HaxeFoundation/haxe/issues/5950), [haxe#5951](https://github.com/HaxeFoundation/haxe/issues/5951)).

#### Add import

[[images/code-actions/add-import.gif]]

#### Change to fully qualified type

[[images/code-actions/fully-qualified.gif]]

### Actions for unused code

There are several code actions that deal with removing unused code:

#### Remove unused import/using

[[images/code-actions/unused-import.gif]]

#### Remove all unused imports/usings

[[images/code-actions/unused-imports.gif]]

#### Remove unused variable

[[images/code-actions/unused-var.gif]]