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

# iTerm2

iTerm2 is an open source replacement for Apple's Terminal. It's highly customizable and comes with a lot of useful features.

## Customization

- Download and import themes from this link: https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/schemes
- Add little transparency and little blur for cool look
- Change the font to 14pt Source Code Pro
- Source Code Pro can be downloaded using Homebrew: `brew tap homebrew/cask-fonts && brew install --cask font-source-code-pro`
- Changed other needed configurations

# ZSH

The Z shell (also known as zsh) is a Unix shell that is built on top of bash (the default shell for macOS) with additional features. It's recommended to use zsh over bash. It's also highly recommended to install a framework with zsh as it makes dealing with configuration, plugins and themes a lot nicer.

- Install zsh by running this command: `brew install zsh`

The configuration file for zsh is called .zshrc and lives in your home folder (~/.zshrc).

## Oh My Zsh

Oh My Zsh is an open source, community-driven framework for managing your zsh configuration. It comes with a bunch of features out of the box and improves your terminal experience.

- Install Oh My Zsh: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
- The installation script should set zsh to your default shell, but if it doesn't you can do it manually: `chsh -s $(which zsh)`
- Add home brew to path so homebrew installed programmes will be able to run from shell: `echo 'PATH="/usr/local/bin:$PATH"' >> ~/.zshrc`

### Configuration

The out-of-the-box configuration is usable but you probably want to customise it to suit your needs. The Official Wiki (https://github.com/ohmyzsh/ohmyzsh/wiki) contains a lot of useful information if you want to deep dive into what you can do with Oh My Zsh, but we'll cover the basics here.

To apply the changes you make you need to either start new shell instance or run: `source ~/.zshrc`

### Plugins

Add plugins to your shell by adding the name of the plugin to the `plugin` array in your `.zshrc`.

`plugins=(git colored-man-pages colorize pip python brew osx zsh-syntax-highlighting zsh-autosuggestions yarn emoji emoji-clock npm npx nvm node postgres react-native vscode xcode)`

You'll find a list of all plugins on the Oh My Zsh Wiki. Note that adding plugins can cause your shell startup time to increase.



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
