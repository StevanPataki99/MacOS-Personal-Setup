# MacOS-Personal-Setup
My personal MacOS setup guide.

This guide is loosely based on this guide:
http://sourabhbajaj.com/mac-setup/

# First Steps

After initial installation and setup:

- iCloud settings (disable iCloud photos backup)
- System Preferences
- Home screen
- Dock(or after all apps are installed)
- MenuBar
- Finder preferences
- Go through apple apps and setup the needed ones
- Download any backedup files/folders

# App Store apps to download:

- Spark
- Battery Monitor
- Be Focused
- Amphetamine

# Xcode

- Download and install Xcode from App Store
- Install Xcode command line tools via terminal and by running this command: 
  `xcode-select --install`
  
# Homebrew

- Before installation you must install Xcode command line tools
- Install homebrew via terminal by running this command: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
- Add home brew to path so homebrew installed programmes will be able to run from shell (this time i will run it in bash_profile but after zsh installation i need to run it again in zsh): `echo 'PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile`
- To see if everything is working restart terminal and run: `brew doctor`
- More info about homebrew in Notion file

## Homebrew cask

Homebrew-Cask extends Homebrew and allows you to install large binary files via a command-line tool. You can for example install applications like Google Chrome, Dropbox, VLC and Spectacle.

### Quick-look plugins

These plugins add support for the corresponding file type to Mac Quick Look (In Finder, mark a file and press Space to start Quick Look). The plugins includes features like syntax highlighting, Markdown rendering, preview of JSON, patch files, CSV, ZIP files and more.

`brew install --cask qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzip webpquicklook suspicious-package`
    
### Main apps installation

  `brew install --cask appcleaner cheatsheet google-chrome visual-studio-code iterm2 notion spotify postman slack skype deluge zoom jetbrains-toolbox microsoft-teams messenger intel-power-gadget macs-fan-control rectangle vlc`

# TEMPORATY

- ZSH
- git

# Programs

- Addobe XD
- Storyboard

# VSCode extensions

- Sublime Matirial theme Dark
- Material Icon Theme
- Better Comments
- Bracket Pair Colorizer
- Colorize
- GitLense
- Highlight Matching Tag
- Import Cost
- open in browser

# Temporary

After initial setup and updates install following programs and configure them.
