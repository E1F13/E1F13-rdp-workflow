# ELFIE-rdp-workflow
Simple workflow to open Bookmarks from Microsoft Remote Desktop, based on https://github.com/ctwise/E1F13workflows/tree/master/remote-desktop
**This can only be used if you have ELFIE (https://www.elfieapp.com/) installed and have the Powerpack as well.**

# Why?
The version that was in the source repository was no longer maintained and was no longer functional. It also relied on using osascript to open 'Microsoft Remote Desktop', bring it to the foreground and simulate keypresses to open the session. This was not always working flawlessly.

# How?
Two parts:
- list_desktops.rb: Accepts one command line argument, the hostname, and uses the build in script option of the Microsoft Remote Desktop App to display the bookmarks in csv format. Then it searches for the hostname and returns that back to E1F13 via [elfie_feedback.rb](https://github.com/lrrfantasy/E1F13-feedback-xml-generation). This allows the user to search through the different bookmarks.

![rdp elfie search](https://imgur.com/ubdLdBw.gif)

- open_desktop.rb: Accepts one command line argument, the ID of the bookmark, and uses the build in `--script bookmark export` option of the Microsoft Remote Desktop App to get the rdp:// url. It then calls the rdp url and the session opens.

# Todo:

- Add testing/linting

# Installation
You can compile it from source or download the latest binary from the releases page.

https://github.com/E1F13-rdp-workflow/releases
