Vshaxe auto-discovers `.hxml` files in the root directory of your project and generates [Tasks](https://code.visualstudio.com/docs/editor/tasks) for them. You can access them with `Tasks` -> `Run Task...`:

![](images/build-tasks/auto-detected-tasks.png)

You can configure one of the tasks to be the "default build task" via `Tasks` -> `Run Build Task...`. This creates a `tasks.json` and allows running that task directly with a shortcut (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> by default).

>**Note**: in projects with multiple `.hxml` files / configurations, it usually makes sense to pick `haxe: active configuration` as your default build task. This then lets you conveniently select the task to be built [with the `Select Configuration` command or the dropdown menu in the status bar](https://github.com/vshaxe/vshaxe/wiki/Commands#haxe-select-configuration).

Output of tasks is printed to the Terminal:

![](images/build-tasks/terminal.png)

Compiler errors that occur during a task's execution are picked up by the "Problems" panel. You can click on them to go to the error's position:

![](images/build-tasks/problems-panel.png)


### Configuration

- `"haxe.executable"` - Which Haxe exectuable to use to run the tasks. See [here](https://github.com/vshaxe/vshaxe/wiki/Configuration#haxe-executable) for more information.
- `"haxe.displayPort"` - Allows connecting to the Language Server's Haxe process for faster compilation. The setting defaults to `"auto"`, meaning that for each new instance of VSCode you open, a new unique port will be picked.
- `"haxe.enableCompilationServer"` - Whether auto-generated tasks should connect to the port picked by `"haxe.displayPort"`. Defaults to `true`.