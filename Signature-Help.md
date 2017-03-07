Signature Help is shown whenever the opening `(` of a function call or the `,` after a function argument is typed. For instance, here it lets us know that `concat()` expects one argument, and that that argument is of type `Array<Int>`:

[[signature-help/concat.png]]

If a method has multiple arguments, signature help will underline the current parameter:

[[signature-help/multiple-args.gif]]

Without this, it would sometimes be hard to tell which expression corresponds to which argument in calls with complex arguments.

Signature Help doesn't only work for methods, but also [enum constructors that have arguments](https://haxe.org/manual/types-enum-constructor.html):

[[signature-help/enum.png]]

If a method has overloads (only possible in [externs](https://haxe.org/manual/lf-externs.html) in Haxe), you can use the up and down keys to switch between them:

[[signature-help/overloads.gif]]