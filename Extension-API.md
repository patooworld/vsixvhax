```haxe
extern class VshaxeAPI {
    /**
     * Register a display argument provider.
     *
     * Display arguments are passed to the Haxe Language Server for completion and used for the dependency explorer.
     *
     * An extension should only register a provider if it handles the current workspace's project type
     * (usually when a matching project file is present, e.g. a `project.xml` in Lime's case).
     * In the case of two competing providers, the user is prompted to select between them.
     *
     * @param name A unique ID to identify the extension. Shown to the user for conflict resolution.
     * @param provider A display argument provider.
     */
    public function registerDisplayArgumentProvider(name:String, provider:DisplayArgumentProvider):Disposable;
}

typedef DisplayArgumentProvider = {
    /**
     * Called when vshaxe selects the provider for providing completion. Might never be called if another provider is active.
     *
     * @param provideArguments A callback that should be cached by the provider, and called whenever display arguments change.
     *        The callback's `String` argument is assumed to be formatted like a HXML file and will be parsed by vshaxe.
     *        `provideArguments` should only be called when necessary.
     */
    public function activate(provideArguments:String->Void):Void;

    /**
     * Called when this display argument provider is no longer active, for instance because the user has chosen to use
     * another provider. The provider is informed about this to stop unnecessary system calls if deactivated.
     *
     * *Note:* a deactivated provider can be activated again!
     */
    public function deactivate():Void;
}
```