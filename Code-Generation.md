> **Note:** the features on this page all require Haxe 4.0.0-preview.4 or newer.

### Auto-Imports

Whenever you select an unimported type from completion, an import is added to the top of the file automatically:

![](images/code-generation/auto-import.gif)

If you'd prefer the fully qualified path to be inserted instead, you can disable auto-imports like this:

```json
"haxe.codeGeneration": {
   "imports": {
       "enableAutoImports": false
   }
}
```

### Expected Type Completion

Expected type completion can be used in places where a certain type is expected. Use the regular completion shortcut (<kbd>Ctrl</kbd>+<kbd>Space</kbd>) to trigger it.

#### Object Literals

For generating object literals, there are two choices: generate an object literal with all fields, or just the ones that are required / non-optional.

![](images/code-generation/expected-type-object-literal.gif)

#### Functions

Expected type completion can also be used in places where a function type is expected:

![](images/code-generation/expected-type-function.gif)

### Override Completion

After typing the `override` keyword, you are offered a list of functions you can currently override. Selecting one of them will generate the code for it, complete with imports.

![](images/code-generation/override-completion.gif)

### Pattern Completion

When selecting an enum constructor from completion inside a pattern (after a `case` in a `switch`), capture variables for the arguments are auto-inserted:

![](images/code-generation/auto-insert-case.gif)

### Configuration

There's a number of ways to customize how generated functions should look like. The following are the default settings, which apply to both [Expected Type Completion](#expected-type-completion) and [Override Completion](#override-completion).

```json
"haxe.codeGeneration": {
    "functions": {
        "anonymous": {
            "argumentTypeHints": false,
            "explicitNull": false,
            "returnTypeHint": "non-void",
            "useArrowSyntax": true
        },
        "field": {
            "argumentTypeHints": true,
            "explicitNull": false,
            "explicitPrivate": false,
            "explicitPublic": false,
            "placeOpenBraceOnNewLine": false,
            "returnTypeHint": "always"
        }
    }
}
```
