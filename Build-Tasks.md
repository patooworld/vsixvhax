Here is an example `tasks.json` file for your `.vscode/` workspace:

```json
{
    "version": "2.0.0",
    "command": "haxe",
    "args": ["build.hxml"],
    "problemMatcher": {
        "owner": "haxe",
        "pattern": {
            "regexp": "^(.+):(\\d+): (?:lines \\d+-(\\d+)|character(?:s (\\d+)-| )(\\d+)) : (?:(Warning) : )?(.*)$",
            "file": 1,
            "line": 2,
            "endLine": 3,
            "column": 4,
            "endColumn": 5,
            "severity": 6,
            "message": 7
        }
    }
}
```

This is the same `tasks.json` file that will be generated when using the ["Initialize VS Code Project..."](/vshaxe/vshaxe/wiki/Commands#haxe-initialize-vs-code-project) command. Pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> will run `haxe build.hxml` and trace any output to the Terminal that is opened:

[[images/build-tasks/terminal.png]]

The `"problemMatcher"` is for detecting compiler errors in the terminal output. These will be shown in the "Problems" view and are clickable:

[[images/build-tasks/error.png]]

**Known issues:** Haxe sometimes outputs relative and sometimes absolute paths, but the problem matcher can only be configured to accept one at a time ([#23](https://github.com/vshaxe/vshaxe/issues/23)).

For further information on the `tasks.json` format, please refer to the [official VSCode documentation](https://code.visualstudio.com/docs/editor/tasks). A section that should be particularly interesting for usage with Haxe is the ability to define [multiple tasks](https://code.visualstudio.com/docs/editor/tasks#_command-and-tasks) (think multiple targets).