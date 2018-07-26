> **Note:** the features on this page will become available with the next version of vshaxe (2.3.0).

VSCode has some basic, indentation-based folding that works for all languages built-in (so you can fold `{}` blocks etc). The Haxe extension however provides a custom folding implementation that better understands Haxe syntax, adding the following features:

### Import Folding

The imports / usings section in a module can be collapsed:

![](images/folding/imports.gif)

### Conditional Compilation Folding

There are folding markers for `#if`, `#else` and `#elseif`, so conditional compilation blocks can be collapsed:

![](images/folding/conditional-compilation.gif)

### Multi-Line String and Array Literal Folding

Multi-line string and array literals can be folded as well:

![](images/folding/array-literal.gif)

![](images/folding/string-literal.gif)

### Region Folding

You can also use single-line comments to define "regions" of code that can be collapsed:

![](images/folding/regions.gif)

The following three styles are supported:

- `// #region <name>` - `// #endregion`
- `// region <name>` - `// end region`
- `// { region <name>` - `// } endregion`

Regions can also be nested.
