### Completion doesn't work at all

If completion features still aren't working after configuring everything (see [Configurations](/vshaxe/vshaxe/wiki/Configuration#configurations-and-display-server) and [Framework Notes](/vshaxe/vshaxe/wiki/Framework-Notes)), there are some steps you can take to find the culprit.

Output from the Haxe Language Server is logged to the Haxe Output Channel. Here's how to reach it and what it might look like when trying to access a class from a dependency vshaxe doesn't know about (missing `-lib json2object` in the display `.hxml` file):

![](images/troubleshooting/output-channel-.gif)

You can get more verbose output by adding the `-v` flag to the compiler arguments in your `settings.json`:

```json
"haxe.displayServer": {
    "arguments": ["-v"]
}
```

With this, the output channel will show the complete display requests sent to Haxe (as well as the full responses).

![](images/troubleshooting/verbose.png)

If you're unable to solve whatever issues you are having after reading the Setup documentation, don't hesitate to ask a question [on our issue tracker](https://github.com/vshaxe/vshaxe/issues/new).

### Completion is slow

If completion works, but is slower than expected, make sure the [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache) is working.

A convenient way to debug slow completion is to use the built-in "Haxe Methods" view (requires Haxe 4.0.0-preview.4 or newer):

```json
"haxe.enableServerView": true
```

This adds a tree view to your explorer with detailed information about what took how much time for a particular method. This is an example of completion working well, with < 100 ms:

![](images/troubleshooting/completion-breakdown.png)

If instead, a lot of time was spent in "typing" and / or "macro" and you do have a [Completion Cache](/vshaxe/vshaxe/wiki/Completion-Cache) built up, that is a likely indicator that too many cached files are being invalidated. Add the following to your settings to get a detailed breakdown of the files that are being invalidated for each request in the Haxe Output Channel:

```json
"haxe.displayServer": {
    "arguments": ["-v"],
    "print": {
        "reusing": true
    }
}
```

---

If completion is slow only _sporadically_, it might be caused by the Haxe server performing garbage collection every so often. This should only be an issue with Haxe version 4.0.0-preview.3 or prior. You can make sure by enabling verbose completion server output (see further down this page for details) and checking if there's any output like this:


```
Compacted memory 13.230s 1541.2MB
```
