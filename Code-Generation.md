There are a lot of plans and ideas for Code Generation, but as it stands, there is only one [Code Action](/vshaxe/vshaxe/wiki/Code-Actions) is available for Code Generation:

### Generate anonymous function

"Generate anonymous function" is made available whenever vshaxe comes across a function in a parameter in [Signature Help](/vshaxe/vshaxe/wiki/Signature-Help).

[[images/code-generation/anon-function.gif]]

When generating parameter names, vshaxe has to "take a best guess" based on the parameter types, as function types in Haxe do not include parameter names. It follows the following rules:

- For `Int`, `Float`, `Bool` and `String`, use single letter-names (`i`, `f`, `b`, `s`)
- For camel-case names (e.g. `BalancedTree`), use the last segment (`tree`)
- For any duplicate names, add numbers at the end (`i1`, `i2`...) 

>**Known issues:** if the parameter type is a `typedef` to a function type, vshaxe is at the moment unable to resolve the underlying function type and will not offer code generation ([#103](https://github.com/vshaxe/vshaxe/issues/103)).

### Configuration

