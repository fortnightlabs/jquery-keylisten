jquery-keylisten
================

A simple keyboard compatibility layer for jquery. Inspired by
[jquery.hotkeys](https://github.com/tzuryby/jquery.hotkeys)

Features
--------

* easy-to-remember key names instead of key codes
* fire a single event so you can use switch for dispatching
* handles key repeats [consistently across
  browsers](http://msdn.microsoft.com/en-us/scriptjunkie/ff928319.aspx)
* listening on the document ignores key events from text accepting
  inputs

Usage
-----

    $(document).keylisten(function(e) {
      var dir = null;
      switch(e.keyName) {
      case "shift+up":
        dir = dir || 'top';
      case "up":
        dir = dir || 'prev';
      case "shift+down":
        dir = dir || 'bottom';
      case "down":
        dir = dir || 'next';
        move(dir, e);
        return false;
      case "enter":
      case "return":
      case "tab":
        select(e);
        return false;
      case "esc":
      case "del":
      case "backspace":
        close();
        return false;
      default:
        refresh();
        break;
      }
    })

See the code for all the keynames.

License
-------
[MIT License](http://www.opensource.org/licenses/mit-license.php)
