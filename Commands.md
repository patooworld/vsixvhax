The vshaxe extension adds the following commands. You can invoke them by pressing <kbd>F1</kbd> or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>/<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> and
typing part of the command name. All commands are prefixed with `Haxe:`:

### Haxe: Initialize VS Code Project...

Scaffolds a very basic Haxe project in an empty workspace. Can also be used on an existing project with `.hxml` files
to generate `.vscode` workspace folder with the build task and example vshaxe configuration.

### Haxe: Restart Language Server

Restarts language server and Haxe completion server. Use if anything goes wrong or to reload haxe-languageserver code
when developing.

Known issues: a new Haxe output channel is added on each restart ([#87](https://github.com/vshaxe/vshaxe/issues/87)).

### Haxe: Select Display Configuration...

Choose the currently active display configuration (see [Configuration](/vshaxe/vshaxe/wiki/Configuration) section for more info).

### Haxe: Run Global Diagnostics Check

Runs diagnostics (unused import / dead code detection) on all files in the workspace.

### Haxe: Toggle Code Lens

En/disables Haxe [Code Lens](https://github.com/vshaxe/vshaxe/wiki/Code-Lens) in your [Configuration](/vshaxe/vshaxe/wiki/Configuration) by flipping the `"haxe.enableCodeLens"` setting.

Known issues: Code Lens only refresh after editing the current file ([#95](https://github.com/vshaxe/vshaxe/issues/95)).