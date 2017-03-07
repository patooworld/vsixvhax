Hover Hints tell you the type of arbitrary expressions you place your mouse cursor over:

[[images/hover-hints/simple.png]]

This feature works very well with [Type Inference](https://haxe.org/manual/type-system-type-inference.html). One of the biggest arguments against type inference it is that be code becomes less readable without explicit type hints. However, if the type is just one mouse movement away, this argument loses some validity.

Hover Hints are also a great way to check documentation. They support both markdown and JavaDoc formatting:

[[images/hover-hints/markdown.png]]

[[images/hover-hints/javadoc.png]]

Hover Hints can even provide documentation for [Compiler Metadata](https://haxe.org/manual/cr-metadata.html):

[[images/hover-hints/metadata.png]]

This information is identical with that found in `haxe --help-metas`.