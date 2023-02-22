i3-alternating-layout
=====================

Scripts to open new windows in i3wm/Sway using alternating layouts (splith/splitv) for each new window. These scripts were made for [/u/ke7ofi](http://www.reddit.com/user/ke7ofi) after they asked a question on how to do this [you can read the question here](http://www.reddit.com/r/i3wm/comments/1sdc39/alternating_horizontal_and_vertical_splitting/).

Installation
------------
Clone this repository.

Then, for i3 add:
```
exec --no-startup-id /path/to/i3-alternating-layout
```
to your `~/.i3/config`.

Or, for Sway add:
```
exec /path/to/alternating
```
to your `~/.config/sway/config`.

Fork Changes
------------
This version has been forked to add an aspect ratio command-line argument.  The previous behavior was to split vertically when the parent window's height is less than the window's width, but now, you may specify a maximum aspect ratio, above which a window will be split vertically.  This is because:

- Many applications are designed with an assumption that the viewport will be wider than it is tall.
- On an ultrawide screen, the default behavior (essentially a max aspect ratio of 1.0) will not recreate a bspwm spiral-style layout - on for example, on a 21:9 screen, the spiral behavior will only start after *two* vertical splits.

To support additional CLI arguments, the script has also been rewritten to use the `argparse` library, instead of `getopt`.

Screenshot
----------

Using regular i3/Sway, creating a window layout like this would involve a lot of `$mod+Return`, `$mod+h` and `$mod+v`. Using this script, you only need to open a bunch of new windows!

![Screenshot](https://github.com/olemartinorg/i3-alternating-layout/raw/master/screenshot.png "Screenshot (1920x1080)")
