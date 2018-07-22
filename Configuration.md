The vshaxe extension supports the following settings. They can be configured in user or workspace settings file (`.vscode/settings.json`):

### Display Configurations and Display Server

```js
{
    "haxe.displayConfigurations": [ // one or more configurations for the haxe completion server
        ["-cp", "src", "-js", "main.js"], // a configuration is array of arguments passed to the completion server
        ["build.hxml"], // hxml file is a normal Haxe argument too
    ],
    "haxe.displayServer": { // configuration for starting haxe completion server itself
        "arguments": ["-v"], // arguments before --wait (-v is useful for debugging)
    }
}
```

Beware that display configurations specified in `"haxe.displayConfigurations"` should only contain arguments suitable for
completion, such as `-cp`, `-lib`, `-D` and target output (`-js`, `-cpp`, etc.). This is particularly important when
specifying an `.hxml` file for completion: make sure it doesn't contain `--next`, `--each` and other arguments
not suitable for completion.

#### Multiple Display Configurations

Multiple display configurations are useful when working with a codebase that is meant
to be compiled for different Haxe targets, or with a different set of defines. If
there is more than one configuration provided in the `"haxe.displayConfigurations"` setting,
when a `.hx` file is open, a selection appears in the status bar allowing to switch current
display configuration:

![](images/configuration/configs.gif)

The same menu can also be shown by using `Haxe: Select Configuration` command from the command palette or a keybinding.

### Haxe Executable

You can change the executable used for [Tasks](/vshaxe/vshaxe/wiki/Tasks) and the display server with the `"haxe.executable"` setting:

```js
"haxe.executable": "C:\\HaxeToolkit\\haxe\\haxe.exe"
```

You can also have more complex settings that include environment variables or OS-specific properties:

```js
"haxe.executable": {
    "path": "haxe", // path to the executable (default: `haxe`)
    "env": { // environment variables for Haxe
        "HAXE_STD_PATH": "/some/path",
        "SOME_VAR": "some_value",
    },
    // platform-specific overrides of the keys above
    // they will be merged into the default configuration
    "windows": {},
    "linux": {},
    "osx": {}
}
```

### Feature-specific configuration

For configuration of specific features, please refer to their respective sub-pages:

- [Tasks](/vshaxe/vshaxe/wiki/Tasks#configuration)
- [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache)
- [Diagnostics](/vshaxe/vshaxe/wiki/Diagnostics#configuration)
- [Signature Help](/vshaxe/vshaxe/wiki/Signature-Help#configuration)
- [Code Generation](/vshaxe/vshaxe/wiki/Code-Generation#configuration)
- [Code Lens](/vshaxe/vshaxe/wiki/Code-Lens)