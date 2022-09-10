Inlay hints feature will show type hints for variables and function return types so you can see what types Haxe infers in each location. 

it also adds parameter names for function calls that show which values get matched with what named parameter for any function call you make.

conditional sections can have inlay hints for every `#end` to show what `#if` condition they belong to.

you can double click on inlay hints to make them permanent (only applies to variables, function return types and conditionals).

![20220523_inlayHints](https://user-images.githubusercontent.com/7204032/189485956-29debaac-e20e-4f58-990b-8b97c39b44c4.gif)

> **note**: inlay hints feature relies on hover requests and it sends one per location. 
depending on number of locations and speed of hover requests it can take a few seconds up to multiple minutes before you see inlay hints. 
VSCode only requests inlay hints for current file and about 2-3 pages above and below current position, which means every scroll or switch to a new file will add another request or cancel previous requests.


## Configuration

you can control inlay hints via `"editor.inlayHints.enabled"` setting (default: on). 

Haxe's inlay hints come with additional settings to fine-tune what inlay hints you want to see:

```json
"haxe.inlayHints": {
	"variableTypes": true,
	"parameterNames": true,
	"parameterTypes": false,
	"functionReturnTypes": true,
	"conditionals": false
}
```
* `variableTypes` - inlay hints showing variable types for `var` or `final` variables (only when no explicit type hint is present)
* `functionReturnTypes` - inlay hints showing return value types in function signatures (only when no explicit type hint is present)
* `parameterNames` -  inlay hints with names of a parameters in a function call
* `parameterTypes` - inlay hints with parameter types in function calls
* `conditionals` - inlay hints for conditionals, showing corresponding `#if` condition for every `#end`

