Vshaxe requires a `.hxml` file to invoke the Haxe code completion engine. The method of aquiring this file depends on the framework you are using (unless it's just a pure Haxe project), but for all of them, you need to add the `.hxml` file(s) to your `settings.json` as shown shown below:

```json
{
    "haxe.displayConfigurations": [
        ["completion.hxml"]
    ]
}
```

If you don't have a `.vscode` workspace set up yet, you can use the ["Initialize VS Code Project..."](/vshaxe/vshaxe/wiki/Commands#haxe-initialize-vs-code-project) command to generate a `settings.json` with all `.hxml` files in the current folder.

Here are some notes on how obtain `.hxml` files with popular Haxe frameworks:

### Lime / OpenFL

A `.hxml` file for completion by can obtained by running `haxelib run lime display <platform> > completion.hxml`. However, these files are generally only suitable for completion, but not building the project, which is necessary to get fast completion via the [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache).

For this reason, it's recommended to use the `.hxml` files that Lime already generates anyway on each build. A `settings.json` for Neko and Flash might look like this:

```json
{
    "haxe.displayConfigurations": [
        ["Export/windows/neko/debug/haxe/debug.hxml"],
        ["Export/windows/neko/release/haxe/release.hxml"],
        ["Export/flash/debug/haxe/debug.hxml"],
        ["Export/flash/release/haxe/release.hxml"]
    ]
}
```

### HaxeFlixel

Flixel supports initializing a `.vscode` workspace via `flixel-tools`, which has the necessary configuration for both completion and debugging. For detailed instructions, please refer to the [official documentation](http://haxeflixel.com/documentation/visual-studio-code/).

### Kha

Like Lime, Kha automatically generates `.hxml` files when building. They are located in `build/project-<platform>.hxml`. 

`settings.json` needs to be adjusted to change the working directory to `build` via `--cwd`:

```json
{
    "haxe.displayConfigurations": [
        ["--cwd", "build", "project-<platform1>.hxml"],
        ["--cwd", "build", "project-<platform2>.hxml"]
    ]
}
```

Problem matcher (`tasks.json` file) also needs to take location of `.hxml` file into account:

```js
"problemMatcher": {
    "fileLocation": ["relative", "${workspaceRoot}/build"],
    // [...]
}
```

### Snow

For Snow, a `.hxml` file can be obtained by running the following command:

```
haxelib run flow info --hxml > completion.hxml
```

### Flambe

For Flambe, a `.hxml` file can be obtained by running the following command:

```
flambe haxe-flags > completion.hxml
```

_____________________

Feel free to file an issue with details for other frameworks. Smoother integration with third-party libraries is planned ([#18](https://github.com/vshaxe/vshaxe/issues/18)).