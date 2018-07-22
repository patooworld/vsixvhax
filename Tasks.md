Vshaxe auto-discovers `.hxml` files in the root directory of your project and generates [Tasks](https://code.visualstudio.com/docs/editor/tasks) for them. You can access them with `Tasks` -> `Run Task...` or by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>:

![](images/build-tasks/auto-detected-tasks.png)

>**Note:** auto-generated tasks use the Haxe executable defined by the [`"haxe.executable"` setting](https://github.com/vshaxe/vshaxe/wiki/Configuration#haxe-executable) and connect to the compilation server by default.

Output of tasks is printed to the Terminal:

![](images/build-tasks/terminal.png)

Compiler errors that occur during a task's execution are picked up by the "Problems" panel. You can click on them to go to the error's position:

![](images/build-tasks/problems-panel.png)


### Configuration

- `"haxe.displayPort"` - Allows connecting to vshaxe's Haxe server process for faster compilation. The setting defaults to `"auto"`, meaning that for each new instance of VSCode you open, a new unique port will be picked.
- `"haxe.enableCompilationServer"` - Whether auto-generated tasks should connect to the port picked by `"haxe.displayPort"`. Defaults to `true`.