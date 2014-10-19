# What is this?

This is a fork of Openbox window manager (http://openbox.org) with the goal of adding more for dynamic content functionality to the Openbox menu. Though Openbox already supports pipe menus, this fork aims to extend that idea to separator, menu and action labels.

# How does it work?

Currently only separator labels are supported (as a proof of concept). You can make use of them by adding a `lexecute` attribute to the `separator` tag in your menu.xml file. The value of the `lexecute` attribute should be a shell command or location of a script file (just like pipe menus).

For example, defining a separator like this:
```
<separator lexecute="date +%T" \>
```
will create a separator menu entry containing the current time.

# Further Development
- Extend support to include menu and action labels, not only separators.
- Add support to periodic updating of label text (e.g. system monitor info that updates while the menu is open).
