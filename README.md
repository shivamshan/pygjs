# pygjs

PyGame in NodeWebkit/Browser

This is a rough draft of something I've been working on for a while, so use it wisely (ALPHA)

Basically, I've always liked the way the pygame library laid out but I knew if I programmed a game in pygame, I'd have to cludgingly port it to whatever OS I want the game to run on, not to mention package up the python into an executable.

So I thought to myself, after discovering the beautiful GameJS library http://gamejs.org/ and the lovely Brython library http://brython.info/ what if I could run pygame more or less in a nodewebkit installation (and even the browser?)

PYGJS was born!  Essentially it is structure like this:

My GameJS implementation here is MODIFIED extensively, you can find out more information at asherwunk/gamejs  It also uses more libraries including, howler.js, gamepad.js, and opentype.js (see asherwunk/gamejs)

I browserify gamebridge.js and output it to game.js like so:

browserify ./gamebridge.js -o game.js

I then include game.js as a script on my HTML file

This creates a gamejs variable on my window, which I then access through Brython

Brython imports pygame, as defined here, which is a python code wrapping GameJS functionality into things more pygame recognizable

You can also import pygjs which currently provides python wrappers to the rest of the GameJS library

# What To Watch Out For

This is NOT an emulator.  In order for your pygame games to run in this environment you WILL have to reprogram parts of it.  FOr instance for images and fonts you'll have to preload these before using them.  You'll also have to modify your game loop probably (as a while forever loop would block everything).

If you're willing to make some modifications, you can program in Python using pygame in the browser (or nodewebkit)

# WHY?

Using the browser as my python interpreter, essentially making JavaScript my OS, I can do anything a browser can do.  This includes using other JavaScript libraries.

NodeWebkit applications are also cross-platform compatible, so I can package the game to run in the browser (potentially), on a phone, and on desktop.

Basically, I get all the benefits of pygame with all the benefits of the browser, yay!

# More About Me

I run a personal blog devoted to all sorts of things at http://wunk.me/  If you want to find out more about me, that's the place to do it.
I also have a page dedicated to this project at http://wunk.me/programming-projects/pygjs

I also have a patreon -ahem-, so if you find this utility and potential future ones like it useful go here: https://www.patreon.com/asherwolfstein to support me.  Thanks!