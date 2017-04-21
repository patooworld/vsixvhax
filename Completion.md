### Field Completion

The simplest and most commonly used form of completion is field / "dot" completion. It is invoked whenever a dot is typed after an identifier to show the available variables, properties and methods for it:

[[images/completion/field.png]]

### Toplevel Completion

Toplevel completion gets its name from showing you the available "top level" identifiers, such as imported types or enum values. It can be invoked manually using <kbd>Ctrl</kbd>+<kbd>Space</kbd> anywhere in the document:

[[images/completion/toplevel.png]]

Toplevel completion is also triggered automatically when typing the `:` in a type hint:

[[images/completion/type-hint.png]]

### Compiler Metadata Completion

Whenever `@:` is typed, a list of [compiler metadata](https://haxe.org/manual/cr-metadata.html) is presented to you:

[[images/completion/metadata.png]]

### `--times` Completion

When you add `--times` (and optionally `-D macro-times`) to your completion `.hxml` (see also: [Display Configurations](/vshaxe/vshaxe/wiki/Configuration#display-configurations-and-display-server)), the times are shown at the top of field and toplevel completion for convenience. This is useful for debugging completion speeds, which can be heavily impacted by careless use of macros or be much slower than they should be if your [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache) isn't working.

[[images/completion/times.png]]