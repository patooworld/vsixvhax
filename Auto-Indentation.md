The Haxe extension extends VSCode's built-in auto indentation to support single line `if` / `else` / `for` / etc, as well as `case` and `default` in `switch`:

![](images/auto-indentation/if.gif)

![](images/auto-indentation/case.gif)

If you're using Allman style indentation with `{` in a new line, this may get in the way sometimes:

![](images/auto-indentation/allman-fail.gif)

There are two ways to avoid this:

- Enable _extended indentation_ to automatically decrease the indent again when typing the `{`.

	```json
	"haxe.enableExtendedIndentation": true
	```
  
	![](images/auto-indentation/allman-success.gif)


	> **Note:** due to the way this feature has to be implemented, this may introduce some typing overhead. It's also incompatible with the Vim extension due to [microsoft/vscode#13441](https://github.com/microsoft/vscode/issues/13441). For these reasons, it's not enabled by default.

- Disable the Haxe extension's indentation rules - this may be preferable if you don't use bracketless `if` / `else` etc. However, you also lose auto indentation for `case` and `default`.

	```json
	"[haxe]": {
		"editor.autoIndent": "brackets"
	}
	```

---

By the way, you can also use [auto-formatting](https://github.com/vshaxe/vshaxe/wiki/Formatting) to automatically adjust the indentation of the entire file.