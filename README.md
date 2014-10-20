# What is this?
This is a fork of the Openbox window manager (http://openbox.org) with the goal of adding more dynamic content functionality to the Openbox menu. Though Openbox already supports this via pipe menus, this fork aims to extend that idea to separator, submenu and action labels.

# How does it work?
Simply add a `lexecute` attribute to any tag in your menu.xml file that usually has a `label` tag. The value of the `lexecute` attribute should be a shell command or location of a script file (just like pipe menus), the results of which will take the place of the tag's original `label`.

For example, defining a separator like this:
```
<separator lexecute="date +%T" \>
```
will create a separator menu entry containing the current time.

Note that `seperator` tags don't need the `label` attribute if a `lexecute` attribute is given. However, for submenus and actions the `label` tag is still necessary to determine the menu keyboard shortcut keys, even though the text will be replaced by the results of the `lexecute` script. In practice it's best to set a `label` that gives a "hint" to what is returned by `lexecute`, as it will not update the shortcut key when run.

# Further Development
- (DONE!) Extend support to include menu and action labels, not only separators.
- Add support to periodic updating of label text (e.g. system monitor info that updates while the menu is open).
