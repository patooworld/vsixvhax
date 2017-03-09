If completion features still aren't working after configuring everything (see [Display Configurations](/vshaxe/vshaxe/wiki/Configuration#display-configurations-and-display-server) and [Framework Notes](/vshaxe/vshaxe/wiki/Framework-Notes)), there are some steps you can take to find the culprit.

>**Note:** while completion for small projects without dependencies might work fine out of the box without any additional setup, for anything more complex you will definitely need to set up a Display Configuration.

Output from the Haxe Language Server is logged to the Haxe Output Channel. Here's how to reach it and what it might look like when trying to access a class from a dependency vshaxe doesn't know about (missing `-lib json2object` in the display `.hxml` file):

[[images/troubleshooting/output-channel-.gif]]

You can get more verbose output by adding the `-v` flag to the compiler arguments in your `settings.json`:

```json
"haxe.displayServer": {
    "arguments": ["-v"]
}
```

With this, the output channel will show the complete display requests sent to Haxe (as well as the full responses).

[[images/troubleshooting/verbose.png]]

>**Note:** if your Haxe project is nested within a subdirectory of your VSCode workspace, you may need to adjust the working directory (`--cwd` argument) of your Display Configuration. This is explained [here](/vshaxe/vshaxe/wiki/Configuration#changing-the-working-directory).

If you're unable to solve whatever issues you are having after carefully reading the Setup documentation, don't hesitate to ask a question [on our issue tracker](https://github.com/vshaxe/vshaxe/issues/new).