Code Lens are a bit of a hidden feature right now, as they are disabled by default. To enable them, add the following to your settings:

```json
"haxe.enableCodeLens": true
```

Alternatively, you can use the [Haxe: Toggle Code Lens](/vshaxe/vshaxe/wiki/Commands#haxe-toggle-code-lens) command for this.

Once enabled, Code Lens tells you how often a particular field or type is referenced, similar to [Find All References](/vshaxe/vshaxe/wiki/Find-All-References).

![](images/code-lens/references.gif)

Code Lens are not just a fancier "Find All References" however. They also include the following information:

- subclasses of classes

  ![](images/code-lens/subclasses.png)

- overrides of methods

  ![](images/code-lens/overrides.png)

- implementers of interfaces

  ![](images/code-lens/implementers.png)

- subinterfaces of interfaces

  ![](images/code-lens/subinterfaces.png)