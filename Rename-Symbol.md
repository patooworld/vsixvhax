"Rename Symbol" (<kbd>F2</kbd>) allows you to rename local variables or function parameters. It's smart enough to deal with shadowing or conflicts with existing field names:

![](images/rename-symbol/rename-conflict.gif)

>**Known issues:**
> - Usages inside of string interpolation are currently not detected ([hxparser#10](https://github.com/vshaxe/hxparser/issues/10)).
> - Shadowing is not yet handled correctly for parameters of Haxe 4 arrow functions.