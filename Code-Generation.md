There are a lot of plans and ideas for Code Generation, but as it stands, there is only one [Code Action](/vshaxe/vshaxe/wiki/Code-Actions) is available for Code Generation:

### Generate anonymous function

"Generate anonymous function" is made available whenever vshaxe comes across a function in a parameter in [Signature Help](/vshaxe/vshaxe/wiki/Signature-Help).

[[images/code-generation/anon-function.gif]]

When generating parameter names, vshaxe has to "take a best guess" based on the parameter types, as function types in Haxe do not include parameter names. Argument name guessing follows these rules:

- For `Int`, `Float`, `Bool` and `String`, use single letter-names (`i`, `f`, `b`, `s`)
- For camel-case names (e.g. `BalancedTree`), use the last segment (`tree`)
- For any duplicate names, add numbers at the end (`i1`, `i2`...) 

>**Known issues:** if the parameter type is a `typedef` to a function type, vshaxe is at the moment unable to resolve the underlying function type and will not offer code generation ([#103](https://github.com/vshaxe/vshaxe/issues/103)).

### Configuration

How a generated anonymous function looks like can be customized. The default settings look like this:

```js
"haxe.codeGeneration": {
    "functions": {
        "anonymous": {
            "argumentTypeHints": false,
            "returnTypeHint": "never"
        }
    }
}
```

The default behavior is to not include any type hints for arguments or return types. Perhaps you prefer a configuration that looks like this instead:

```js
"haxe.codeGeneration": {
    "functions": {
        "anonymous": {
            "argumentTypeHints": true,
            "returnTypeHint": "always"
        }
    }
}
```

Which will lead to this behavior:

[[images/code-generation/anon-function-with-types.gif]]

Besides `"never"` and `"always"`, `"returnTypeHint"` has a third option: `"non-void"`. With this, the return type hint will only be added if the return type is not `Void`.