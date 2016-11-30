Version 1.0.0 is the biggest release of vshaxe to date. Here's a quick overview of the most interesting new features:

### Code Actions

When referencing a type not yet imported, you can trigger a code action to do just that.

![](http://i.imgur.com/JyIlDDk.gif)

Alternatively, you may also use "Change to" to use the fully qualified path instead:

![](http://i.imgur.com/jvWF3gT.gif)

On the other hand, if you have _unused_ imports or usings, you can remove them with a single action:

![](http://i.imgur.com/AurAeFE.gif)

In the same fashion, you can remove code doesn't do anything, like unused variables:

![](http://i.imgur.com/HxeXtfJ.gif)

### Completion Cache

When starting up, vshaxe now builds a completion cache. For projects with large dependencies, this can make a huge difference - for instance, the field completion response time went from ~750 ms to just around 100 ms in an empty Flixel project.

![](http://i.imgur.com/IHelA6C.gif)

You can see the difference by disabling the completion cache (`"haxe.buildCompletionCache": false`) and restarting vshaxe. Note: add `--times` to your `.hxml` to see the completion times.

### Completion

Completion now triggers on `@` to provide completion for compiler metadata:

![](http://i.imgur.com/KPguJJC.gif)

Similarly, `:` now triggers type hint completion:

![](http://i.imgur.com/b5p6xny.gif)

And finally, you can get completion for structure fields:

![](http://i.imgur.com/SIhmJzG.gif)

### Workspace Symbols

With `Ctrl+T`, you can now search for symbols project-wide, including Haxelib dependencies and the standard library.

![](http://i.imgur.com/OYuc21X.gif)

### Hover Hints

Hover hints now include documentation and support Markdown formatting. JavaDoc comments are parsed and formatted accordingly.

![](http://i.imgur.com/KQsibfO.gif)

Hover hints now also work on compiler metadata.

![](http://i.imgur.com/6eqwSKG.gif)

### Code Lens

Code Lens tell you how often a field is referenced, how often a function has been overriden, how often an interface has been implemented etc. at one quick glance:

![](http://i.imgur.com/KzwbrnE.gif)

![](http://i.imgur.com/W172kIV.gif)

Right now, this feature is opt-in and needs to be enabled with `"haxe.enableCodeLens": true`.