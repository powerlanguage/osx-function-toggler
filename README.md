# OSX Function Toggler

![Function Toggler Icon](https://raw.githubusercontent.com/powerlanguage/osx-function-toggler/master/fn-icon-small.png)

App wrapping an automater service to toggle the `Use all F1, F2 as standard keys` checkbox in keyboard preferences in OS X.

[Download it here](https://github.com/powerlanguage/osx-function-toggler/raw/master/function-toggle.dmg)

You'll need to allow the app to control your computer in security preferences:

![Security Preferences](https://raw.githubusercontent.com/powerlanguage/osx-function-toggler/master/security-pane.png)

This is what the script actually does:

```
tell application "System Preferences"
    reveal anchor "keyboardTab" of pane "com.apple.preference.keyboard"
end tell
tell application "System Events" to tell process "System Preferences"
    click checkbox 1 of tab group 1 of window 1
end tell
quit application "System Preferences"
```
