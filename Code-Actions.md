When a Code Action is available for the current selection / cursor position, this is indicated by a light bulb to the left of the editor:

![](images/code-actions/light-bulb.png)

To show the available actions, either click the light bulb or press <kbd>Ctrl</kbd>+<kbd>.</kbd>. This will open a popup menu:

![](images/code-actions/popup_.png)

In case you want to change the default shortcut, the `command` for this keybinding is `"editor.action.quickFix"`.

Here is an overview over all Code Actions that currently exist:

### Imports

#### Add import

![](images/code-actions/add-import_.gif)

#### Change to fully qualified type

![](images/code-actions/fully-qualified_.gif)

### Unused Code

#### Remove unused import/using

![](images/code-actions/unused-import_.gif)

#### Remove all unused imports/usings

![](images/code-actions/unused-imports_.gif)

#### Remove unused variable

![](images/code-actions/unused-var_.gif)

### Compiler Errors

In some cases, simple compiler errors can be fixed with a Code Action:

#### Invalid package

![](images/code-actions/invalid-package_.gif)

#### Typo suggestions

![](images/code-actions/typo-suggestion_.gif)

### Configuration

- `"editor.codeActionsOnSave"` - Code Actions to be applied when the file is saved. This can be used to trigger the [Remove all unused imports/usings](#remove-all-unused-importsusings) code action on save:
    
	```json
    "editor.codeActionsOnSave": {
        "source.organizeImports": true
	}
	```
