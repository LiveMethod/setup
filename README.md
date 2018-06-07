# New Machine Setup
Setting up a new machine is a hassle. For months, I'll go to run something that I take for granted that isn't yet on the machine. This guide aims to shorten that process.

## The big ones

#### Brew
Install brew to install other things. Computers!

Install with `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

#### Pip
Install pip to install other things.

Install with `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py` which will download a file to wherever your terminal's pointing.

Run this file with `python get-pip.py`. Remember to delete the script when you're finished.

## The not so big ones

#### Watch
Watch runs commands repeatedly (eg `watch make`).
Install with `brew install watch`

The default interval is 2 seconds. specify it with `-n` as in `watch -n 10 make` to run `make` every 10 seconds.

#### When Changed
[when-changed](https://github.com/joh/when-changed) runs a terminal command when a watched file changes.

Install with `pip install when-changed`

Use like `when-changed FILE/DIR COMMAND` eg `when-changed ./src make`

FILE can be a directory. Watch recursively with -r. Use %f to pass the filename to the command.

#### Markdown Quicklook
[QLMarkdown](https://github.com/toland/qlmarkdown) renders markdown files instead of the filetype logo when previewing a file with spacebar on OSX. Magical.

Install with `brew cask install qlmarkdown`

#### Divvy
[Divvy](http://mizage.com/divvy/) rearranges windows based on a grid. My default shortcut is `opt+cmd+d` with `cmd+right` and `cmd+left` to send windows to screen halves. The license is in 1password.

#### Node Version Manager
[NVM](https://github.com/creationix/nvm) allows multiple installs of different node versions on a system, which is helpful when older libs are not forward compatible.
Install with `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash`

Get the latest node with `nvm install node`.

Get a specificed version with `nvm install x.xx.xx` (if you're not picky about the exact version, you can just specify a major version like eg 7)

Use the installed version with `nvm use node`.

#### VLC
[VLC](https://www.videolan.org/vlc/index.html) will play anything you're brave enough to feed it.

## Editor

#### Sublime Package Manager
Install [Sublime Package Manager](https://packagecontrol.io/installation) to install other things.

Open it with `cmd+shift+p` and "install" to filter to the package browser.

#### Syntax Highlighting
Less
Sass
Babel (for ES6 and JSX)
Pug

## System Settings

#### Allow apps from anywhere
The security settings panel hides the option to allow app installs from "anywhere". The feature still exists under the hood, and prevents having to open settings to authorize every new app.
`sudo spctl --master-disable`
