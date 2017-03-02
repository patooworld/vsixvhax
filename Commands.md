The vshaxe extension adds the following commands. You can invoke them by pressing `F1` or `Ctrl-Shift-P`/`Cmd-Shift-P` and
typing part of the command name. All commands are prefixed with `Haxe:`.

### Initialize VS Code Project

Scaffolds a very basic Haxe project in an empty workspace. Can also be used on an existing project with `.hxml` files
to generate `.vscode` workspace folder with the build task and example vshaxe configuration.

### Restart Language Server

Restarts language server and Haxe completion server. Use if anything goes wrong or to reload haxe-languageserver code
when developing.

### Select Display Configuration

Choose the currently active display configuration (see [Configuration](/vshaxe/vshaxe/wiki/Configuration) section for more info).

### Run Global Diagnostics Check

Runs diagnostics (unused import / dead code detection) on all files in the workspace.