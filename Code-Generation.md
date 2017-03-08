There are a lot of plans and ideas for Code Generation, but as it stands, there is only one [Code Action](/vshaxe/vshaxe/wiki/Code-Actions) is available for Code Generation:

### Generate anonymous function

"Generate anonymous function" is made available whenever vshaxe comes across a function in a parameter in [Signature Help](/vshaxe/vshaxe/wiki/Signature-Help).

[[images/code-generation/anon-function.gif]]

**Known issues:** if the parameter type is a `typedef` to a function type, vshaxe is at the moment unable to resolve the underlying function type and will not offer code generation ([#103](https://github.com/vshaxe/vshaxe/issues/103)).

### Configuration