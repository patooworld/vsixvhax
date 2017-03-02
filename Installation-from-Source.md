If you want to contribute to vshaxe, or just prefer working from source, you can follow these steps to install vshaxe from GitHub:

1. Navigate to the extensions folder (`C:\Users\<username>\.vscode\extensions` on Windows, `~/.vscode/extensions` otherwise)
2. _Recursively_ clone this repo: `git clone --recursive https://github.com/vshaxe/vshaxe`.
3. Change current directory to the cloned one: `cd vshaxe`.
4. Do `npm install` (to install `vscode-languageclient` module required to connect to the language server).
5. Install the haxelib dependencies (see [.travis.yml](.travis.yml))
6. Do `haxe build.hxml` (that will build both client and server)
7. After modifying and rebuilding language server, reload it with the `Haxe: Restart language server` command (`Ctrl+Shift+P` to open the command palette).
8. After modifying and rebuilding the extension itself, restart VSCode, reload the window or run a debug instance with F5 ([standard vscode workflow](https://code.visualstudio.com/docs/extensions/debugging-extensions)).

Also to be sure to check out the [vshaxe-debug-tools](https://github.com/vshaxe/vshaxe-debug-tools) extension, which includes some tools to aid the development of vshaxe.