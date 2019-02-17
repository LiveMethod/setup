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

Use like `when-changed [flags] [FILE/DIR] [COMMAND]` eg `when-changed -r ./src make`

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

#### Disable Update Checks

`command + ,` to bring up settings. In user settings json, add flag `"update_check": false`

#### Syntax Highlighting
Less
Sass (the Sass package has an SCSS mode that is good. The standalone SCSS package [textmate] does not highlight properly)
Babel (for ES6 and JSX)
Pug

#### Editor config
EditorConfig

## System Settings

#### Allow apps from anywhere
The security settings panel hides the option to allow app installs from "anywhere". The feature still exists under the hood, and prevents having to open settings to authorize every new app.
`sudo spctl --master-disable`

#### Show hidden files

`defaults write com.apple.finder AppleShowAllFiles YES` from anywhere
relaunch finder (opt/alt + right click the logo or from the force quit menu)

#### Config github.com and github enterprise on the same machine
Config the machine for one env (eg git.corp.bigCo) that will be used by default.

In `~/.ssh/config` add the following

`
Host github.com
  HostName {NON-DEFAULT DOMAIN (eg github.com if git.corp.bigCo is the default)}
  PreferredAuthentications publickey
  IdentityFile {PATH TO ALTERNATIVE KEY}
  IdentitiesOnly yes
`

#### Disable Dock Icon Bounce

In terminal
`defaults write com.apple.dock no-bouncing -bool TRUE` to disable bounce
`killall Dock` to kill (will relaunch automatically)
Same command set false to reverse.

## Chrome Extensions

#### Screenshots
[Full Page Screen Capture](https://chrome.google.com/webstore/detail/full-page-screen-capture/fdpohaocaechififmbbbbbknoalclacl?hl=en-US)
[uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en-US)
[AdBlock Plus](https://chrome.google.com/webstore/detail/adblock-plus/cfhdojbkjhnklbpkdaibdccddilifddb?hl=en-US)
