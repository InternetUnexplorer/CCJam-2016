# FAR - Remote Shell for CC
[![forthebadge](http://forthebadge.com/images/badges/compatibility-ie-6.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/does-not-contain-treenuts.svg)](http://forthebadge.com)

Far is a program that allows you to access a shell session on a remote computer. Made with <3 by InternetUnexplorer for CCJam 2016.
## Features
##### Intelligent terminal support
Far intelligently manages the output of the remote terminal to display it on your screen in an intuitive way.
- If the remote computer has a screen larger than the one you are connecting with, Far will capture the whole screen, and allow you to quickly move your view around to see the whole screen
- If the remote computer has a screen smaller than the one you are connecting with, Far will center it on your screen
- If the remote computer does not have color, your session will not be in color. If the remote computer does have color, but your device does not, then you will be presented with an error message, to prevent incompatible displays.
- All of Far's UI is optimized for variable screen sizes, with compatible and minified messages for small displays

##### Accurate images with low latency
Far forwards ALL of the terminal events on the remote computer to yours, so you see exactly what is on the remote computer, no exceptions. Far also sends messages in batches and intelligently manages how many messages to send at once to make sure that you receive realtime responses while making sure that no signals are lost.

##### Easy setup
Far is a one file program, so there are no extra dependencies and you don't need an installer. The server and client are also in the same file, allowing you to host and connect without needing two separate files.

##### Lots of uses
Far is very versatile, and can be used to
- Debug a friend's program on a server without having to go to their computer
- Connect to computers in hard-to-get to places (Allows you to cover up the computer running a monitor)
- Play games/movies/present on a big screen (Because if you have to stand next to the computer controlling the monitor you can't _really_ see the monitor very well)
- Access files, programs, etc 
- Debug clusters of computers without having to right-click on each one individually

... And a bunch of other things I didn't think of here

## Setup
Download the latest version using `wget https://github.com/InternetUnexplorer/CCJam-2016/blob/master/far far`
> Note: Make sure that you only have one instance of the server/client running on your machine at a time, or else things will get weird!

##### If you want to _host:_
- First we have to setup a password to connect the server. Run `far password` and follow the prompts.
- Now run `far server` to start the server! It's that easy!
- If you want FAR to start when you start your computer, consider putting something in `startup`, such as `shell.openTab("far", "server")` if you have multishell, or maybe just `shell.run("far", "server")` to have a dedicated Far server.

##### If you want to _connect:_
- Run `far client <ID>`, with `<ID>` being the ID of the computer you want to connect to.
> Note: If the remote terminal does not fit on your screen, you can use `SHIFT+ALT+Arrow Keys` to scroll around :)

- Do stuff on the remote computer. `redirection` and `paint` are my favorites :)
- When you want to disconnect, exit the shell by typing `exit` or just using CTRL+T

## Troubleshooting / Advanced
If you want to change more advanced properties, such as the primary prompt color or the network timeout, these are constants located at the top of the program. If you want to fork this, that's awesome!

If you are having problems:
- Timed out: Make sure that the server is running on the remote computer. If you have just lost connection with the server, it may take a second or two to realize that you are no longer connected and reset.
- I get a blank screen, what do I do? Terminate the program and reconnect, the problem should be fixed :)
- How do I disconnect!?!? The connection will close when the shell session associated with it has exited. Try running CTRL+T on the remote shell, or just type `exit`.
- Stuff not described here: Contact me or open an issue and submit relevant details. Thanks! (Or maybe, if you're super awesome and know how to fix the bug, you could fork and PR!)
