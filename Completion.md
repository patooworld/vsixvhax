Completion is triggered automatically when typing certain trigger characters. It can also be invoked manually with <kbd>Ctrl</kbd>+<kbd>Space</kbd>.

### Field Completion

The simplest and most commonly used form of completion is field / "dot" completion. It is invoked whenever a dot is typed after an identifier to show the available variables, properties and methods for it:

![](images/completion/field.png)

### Toplevel Completion

Toplevel completion gets its name from showing you the available "top level" identifiers, such as imported types or enum values. It usually needs to be triggered manually.

![](images/completion/toplevel.png)

### Type Hint Completion

Completion is triggered automatically when typing the `:` in a type hint, showing the available types:

![](images/completion/type-hint.png)

### Compiler Metadata Completion

When typing `@`, the available [compiler metadata](https://haxe.org/manual/cr-metadata.html) is listed:

![](images/completion/metadata.png)