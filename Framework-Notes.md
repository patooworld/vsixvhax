Some frameworks support the creation of `.hxml` files, which is necessary to run the Haxe code completion engine. Below is a list of how you can get an `.hxml` file from various frameworks.

Framework     | How to get .hxml                      | Example usage
------------- | --------------------------------------|------------------------
Lime / OpenFL | `haxelib run lime display <platform>` | `haxelib run lime display linux > completion.hxml`
Snow          | `haxelib run flow info --hxml`        | `haxelib run flow info --hxml > completion.hxml`
Flambe        | `flambe haxe-flags`                   | `flambe haxe-flags > completion.hxml`

You then need to add `completion.hxml` to `haxe.displayConfigurations` in `settings.json` as shown below:

```json
{
    "haxe.displayConfigurations": [
        ["completion.hxml"]
    ]
}
```

**Kha** generates `.hxml` files automatically as `build/project-<platform>.hxml` on each build (so make to sure to build at least once). Also, `settings.json` needs to be adjusted to use the `build` directory:

```json
{
    "haxe.displayConfigurations": [
        ["--cwd", "build", "project-<platform1>.hxml"],
        ["--cwd", "build", "project-<platform2>.hxml"]
    ]
}
```

Problem matcher (`tasks.json` file) also needs to take location of hxml file into account:

```js
"problemMatcher": {
    "fileLocation": ["relative", "${workspaceRoot}/build"],
    // [...]
}
```

For **Flixel**, please refer to [this](http://haxeflixel.com/documentation/visual-studio-code/) document. `flixel-tools` supports initializing a `.vscode` workspace for you.

Feel free to file an issue with details for other frameworks. Smoother integration with third-party libraries is planned ([#18](https://github.com/vshaxe/vshaxe/issues/18)).