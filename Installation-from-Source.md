If you want to contribute to vshaxe, or just prefer working directly from source, you can follow these steps to install vshaxe from GitHub:

1. Navigate to the extensions folder (`C:\Users\<username>\.vscode\extensions` on Windows, `~/.vscode/extensions` otherwise)
2. _Recursively_ clone this repo: `git clone --recursive https://github.com/vshaxe/vshaxe`.
3. Change current directory to the cloned one: `cd vshaxe`.
4. Install the build tool: `haxelib git vshaxe-build https://github.com/vshaxe/vshaxe-build`
5. To build both client and server in debug mode (as well as install all dependencies):

    ```
    haxelib run vshaxe-build --target vshaxe --debug --mode both
    ```

6. After modifying and rebuilding language server, reload it with the `Haxe: Restart language server` command (`Ctrl+Shift+P` to open the command palette).
7. After modifying and rebuilding the extension itself, restart VSCode, reload the window or run a debug instance with F5 ([standard vscode workflow](https://code.visualstudio.com/docs/extensions/debugging-extensions)).

Also to be sure to check out the [vshaxe-debug-tools](https://github.com/vshaxe/vshaxe-debug-tools) extension, which includes some tools to aid the development of vshaxe.