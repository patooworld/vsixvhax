Vshaxe auto-discovers `.hxml` files in the root directory of your project and generates build tasks for them. You can access them with `Tasks` -> `Run Build Task` or by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>:

![](images/build-tasks/auto-detected-tasks.png)

>**Note:** auto-generated tasks use the Haxe executable defined by the [`"haxe.executable"` setting](https://github.com/vshaxe/vshaxe/wiki/Configuration#haxe-executable) and connec to the compilation server by default.

Output of tasks is printed to the Terminal:

![](images/build-tasks/terminal.png)

Compiler errors that occur during task execution are picked up by the "Problems" panel. You can click on them to go to the error's position:

![](images/build-tasks/problems-panel.png)
