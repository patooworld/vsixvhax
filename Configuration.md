The vshaxe extension supports the following settings. They can be configured in user or workspace settings file (`.vscode/settings.json`):

### Display Configurations and Display Server

```js
{
    "haxe.displayConfigurations": [ // one or more configurations for the haxe completion server
        ["-cp", "src", "-js", "main.js"], // a configuration is array of arguments passed to the completion server
        ["build.hxml"], // hxml file is an normal haxe argument too
    ],
    "haxe.displayServer": { // configuration for starting haxe completion server itself
        "haxePath": "haxe", // path to the executable (default: `haxe`)
        "arguments": ["-v"], // arguments before --wait (-v is useful for debugging)
        "env": { // environment variables for the completion server
            "HAXE_STD_PATH": "/some/path",
            "SOME_VAR": "some_value",
        },

        // platform-specific overrides of the keys above
        // they will be merged into the default configuration
        "windows": {},
        "linux": {},
        "osx": {}
    }
}
```

Beware that display configurations specified in `"haxe.displayConfigurations"` should only contain arguments suitable for
completion, such as `-cp`, `-lib`, `-D` and target output (`-js`, `-cpp`, etc.). This is particularly important when
specifying an `.hxml` file for completion: make sure it doesn't contain `-cmd`, `--next`, `--each` and other arguments
not suitable for completion.

Multiple display configurations are useful when working with a codebase that is meant
to be compiled for different Haxe targets, or with a different set of defines. If
there is more than one configuration provided in the `"haxe.displayConfigurations"` setting,
when a `.hx` file is open, a selection appears in the status bar allowing to switch current
display configuration:

[[images/configuration/configs.gif]]

The same menu can also be shown by using `Haxe: Select Display Configuration` command from the command palette or a keybinding.

### Feature-specific configuration

For configuration of specific features, please refer to their respective sub-pages:

- [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache#how-do-i-disable-it)
- [Diagnostics](/vshaxe/vshaxe/wiki/Diagnostics#configuration)
- [Code Generation](/vshaxe/vshaxe/wiki/Code-Generation#configuration)