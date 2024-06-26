>**IMPORTANT**: vshaxe requires Haxe 3.4.0 or newer and works best with [the latest Haxe 4 release](https://haxe.org/download/).

The easiest way to install the latest vshaxe release is by searching the VSCode marketplace for "Haxe":

![](images/installation/marketplace.gif)

Alternatively, press <kbd>Ctrl</kbd>+<kbd>P</kbd> and enter `ext install nadako.vshaxe`.

However, instead of installing vshaxe directly, you might want to consider installing the [Haxe Extension Pack](https://marketplace.visualstudio.com/items?itemName=vshaxe.haxe-extension-pack) instead. Apart from vshaxe itself, it also contains several debuggers (HXCPP, HashLink, Flash) and [codedox](https://marketplace.visualstudio.com/items?itemName=wiggin77.codedox) (for doc comment generation) extensions.

Some frameworks have dedicated extensions that integrate with vshaxe:

- [Lime](https://marketplace.visualstudio.com/items?itemName=openfl.lime-vscode-extension)
- [Kha](https://marketplace.visualstudio.com/items?itemName=kodetech.kha-extension-pack)

### From Source

If you want to contribute to vshaxe, or just prefer working directly from source, you can follow these steps to install vshaxe from GitHub.

1. Navigate to the extensions folder (`C:\Users\<username>\.vscode\extensions` on Windows, `~/.vscode/extensions` otherwise)
2. Remove the existing marketplace installation of vshaxe if present, since it would override the version checked out from source (a folder named `nadako.vshaxe-<version>`).
3. Clone this repo, as well as the extension for the `vshaxe-build` build tool:

    ```
    git clone https://github.com/vshaxe/vshaxe --recursive
    git clone https://github.com/vshaxe/vshaxe-build
    ```

4. Change current directory to the cloned one:

   ```
   cd vshaxe
   ```

5. Install the dependencies:

   ```
   npm install
   ```

6. To build both client and server in debug mode:

    ```
    npx lix run vshaxe-build -t vshaxe --debug
    ```
  
    After the initial build, the usual workflow is to rebuild vshaxe using the `vshaxe (debug)` [build task](/vshaxe/vshaxe/wiki/Build-Tasks) (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>). **Note:** this requires having the [lix extension](https://marketplace.visualstudio.com/items?itemName=lix.lix) installed.

    ![](images/installation/build-task.png)

7. To test changes to the Haxe Language Server, you can reload it with the [Haxe: Restart language server](/vshaxe/vshaxe/wiki/Commands#haxe-restart-language-server) command.
8. To test changes to the extension itself, restart VSCode, reload the window or run a debug instance with <kbd>F5</kbd> ([standard vscode workflow](https://code.visualstudio.com/docs/extensions/debugging-extensions)).

Also to be sure to check out the [vshaxe-debug-tools](https://github.com/vshaxe/vshaxe-debug-tools) extension, which includes some tools to help with the development of vshaxe.