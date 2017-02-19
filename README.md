use-open-browser
================

Linux shell script run instead of default browser with a url, chooses browser to open with based on currently open browser with preference/optionally url-pattern controlled choice

Not for the technically inexperienced in Linux/config file manual editing.

INSTALL
-------
Place use-open-browser and use-open-browser.desktop files here. Yes, there's no package for it or automatic install/uninstall yet. I've built rpm's by hand before but deb's, not really, was a long time ago I did stuff with 'em.

* /usr/share/applications/use-open-browser.desktop
* /usr/bin/use-open-browser

Then use the regular "default applications" setting (the "Details" item in "All Settings" in Ubuntu with Unity, ie. 12.10 onwards, the 2nd item down on the left - typing "details" into the unity search bar will find it) to change your default browser to "Use Active Web Browser".

CONFIGURE
---------
Local config file in your $HOME will override any in /etc, it tries to source the following config scripts (ie must be in 'sh' style NAME=value format, one name per line is best):

* /etc/use-open-browser.cf
* $HOME/.use-open-browser.cf

It may also be run manually on the command line with a url, to test or obtain specific behaviour. Though using gnome-open or xdg-open or your desktop's equivalent with the url as parameter is far more portable and safer and works when use-open-browser isn't installed :)

ERRORS
------
If the given url doesn't match, it will attempt to report the error with an error dialog for your system, based on ubuntu/gnome usage at present, and via the terminal if it can't trivially find the display manager to open a window with.

-v option on the command-line (given before a url, careful to quote it if needed) may help explain what its doing; --dry will just output the command it would have run without actually opening the url in a browser each time.

Beware: it is currently buggy, but less so than the first release. You may see failures or wrong browsers opened in some circumstances, please report any patterns you see (along with your configuration, otherwise its not very helpful) to John Garner via my github (jgbreezer) or email (same account name at gmail.com)
