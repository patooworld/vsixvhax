The vshaxe extension adds the following commands. You can invoke them by pressing <kbd>F1</kbd> or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>/<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> and
typing part of the command name. All commands are prefixed with `Haxe`:

### Haxe: Initialize VS Code Project...

Scaffolds a very basic Haxe project in an empty workspace. Can also be used on an existing project with `.hxml` files
to generate `.vscode` workspace folder with the build task and example vshaxe configuration.

[[images/commands/initialize-vscode-project-.gif]]

### Haxe: Restart Language Server

Restarts the language server and the Haxe completion server. Use it if anything goes wrong or to reload haxe-languageserver's code
after recompiling it.

>**Known issues:** a new Haxe output channel is added on each restart ([#87](https://github.com/vshaxe/vshaxe/issues/87)).

### Haxe: Select Display Configuration...

Choose the currently active display configuration (see [Configuration](https://github.com/vshaxe/vshaxe/wiki/Configuration#display-configurations-and-display-server) section for more info).

### Haxe: Run Global Diagnostics Check

Runs [Diagnostics](/vshaxe/vshaxe/wiki/Diagnostics) on all files in the workspace.

>**Known issues:** It's not obvious when a global diagnostics run has finished, since the problems view is not opened afterwards ([#38](https://github.com/vshaxe/vshaxe/issues/38)).

### Haxe: Toggle Code Lens

En/disables Haxe [Code Lens](/vshaxe/vshaxe/wiki/Code-Lens) in your [Configuration](/vshaxe/vshaxe/wiki/Configuration) by flipping the `"haxe.enableCodeLens"` setting.

[[images/commands/toggle-code-lens-.gif]]

>**Known issues:** Code Lens only refresh after editing the current file ([#95](https://github.com/vshaxe/vshaxe/issues/95)).