# MacOS-Personal-Setup
My personal MacOS setup guide.

This guide is loosely based on this guide:
http://sourabhbajaj.com/mac-setup/

# First Steps

After initial installation and setup:

- Check for MacOS updates
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
- Instapaper
- Instapaper Save
- 1Password
- iStatsMenues

# Apps to download from internet:

- Logitech Options
- Ghub
- Messenger

# Xcode

- Download and install Xcode from App Store
- Install Xcode command line tools via terminal and by running this command: 
  `xcode-select --install`

# Rosseta 2 & Rosseta-Terminal

- Install Rosseta 2 via terminal command for x86_64 translation:
  `/usr/sbin/softwareupdate --install-rosetta --agree-to-license`
- Create Rosseta-Terminal for running x86_64 terminal commands and programs: 
  `Go to your “Applications” folder on Finder → right click Terminal in the “Utilities” folder → Duplicate → rename to “Rosetta Terminal” → Get Info → Open using Rosetta`

# Homebrew

- Before installation you must install Xcode command line tools
- Install homebrew via terminal by running this command: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
- Run command above in regular terminal and rosseta-terminal so i can install both x86_64 and arm64 applications via homebrew
- After zsh installation and if you want in bash add path to ARM Homebrew by adding this line in (zsh: `~/.zshrc` bash: `~/.bash_profile`): `export PATH="/opt/homebrew/bin:/usr/local/bin:$PATH"`
- And if you want to have access to x86_64 based cask's add this alias for x86_64 based Homebrew in zsh `~/.zshrc`: `brewr: aliased to arch -x86_64 /usr/local/bin/brew`
- Test if both Brew's work by running this commmands: for arm `$ which brew`, for x86_64 `$ which brewr` and check if they return correct paths
- To see if everything is working restart terminal and run: `brew doctor`
- More info about homebrew in Notion file

## Homebrew cask

Homebrew-Cask extends Homebrew and allows you to install large binary files via a command-line tool. You can for example install applications like Google Chrome, Dropbox, VLC and Spectacle.

### Main apps installation
  
  

  Arm based apps: `brew install --cask iterm2 notion spotify rectangle cheatsheet google-chrome visual-studio-code postman paw fork slack jetbrains-toolbox vlc tldr macs-fan-control todoist fantastical arc raycast zoom`
  
  x86_64 based apps: `brewr install --cask deluge microsoft-teams messenger steam`

# iTerm2

iTerm2 is an open source replacement for Apple's Terminal. It's highly customizable and comes with a lot of useful features.

## Customization

- Download and import themes from this link: https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/schemes
- Add little transparency and little blur for cool look
- Change the font to 14pt Source Code Pro
- Source Code Pro can be downloaded using Homebrew: `brew tap homebrew/cask-fonts && brew install --cask font-source-code-pro`
- Change keys preset to `Natural Text Editing`
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
- Import `.zshrc` file from git repo to local `.zshrc` file

### Configuration

The out-of-the-box configuration is usable but you probably want to customise it to suit your needs. The Official Wiki (https://github.com/ohmyzsh/ohmyzsh/wiki) contains a lot of useful information if you want to deep dive into what you can do with Oh My Zsh, but we'll cover the basics here.

To apply the changes you make you need to either start new shell instance or run: `source ~/.zshrc`

### Plugins

Add plugins to your shell by adding the name of the plugin to the `plugin` array in your `.zshrc`.

`plugins=(git colored-man-pages colorize pip python brew osx zsh-syntax-highlighting zsh-autosuggestions yarn emoji emoji-clock npm npx nvm node postgres react-native vscode xcode)`

You'll find a list of all plugins on the Oh My Zsh Wiki. Note that adding plugins can cause your shell startup time to increase.

### Powerlevel10k

Powerlevel10k is cool plugin/theme for iterm.

For installation follow the `Manual guide` on this link:

https://github.com/romkatv/powerlevel10k

If powerlevel10k dosent work then setup regular theme from section below.

### Themes

Changing theme is as simple as changing a string in your configuration file. The default theme is robbyrussell. Just change that value to change theme, and don't forget to apply your changes.

`ZSH_THEME=awesomepanda`

### Tree command

tree is a recursive directory listing command that produces a depth indented listing of files.

To install the latest version, use homebrew:
`brew install tree`

### ack command

ack is a search tool designed for code. It's built to be a replacement for grep with higher speed and more options.

To install the latest version, use homebrew:
`brew install ack`

# Git

- Installation: `brew install git`
- When done, to test that it installed properly you can run: `git --version`
- And `which git` should output: `/usr/local/bin/git`
- Next, we'll define your Git user (should be the same name and email you use for GitHub):
`git config --global user.name "Your Name Here"`
`git config --global user.email "your_email@youremail.com"`
They will get added to your .gitconfig file.

To prevent git from asking for your username and password every time you push a commit you can cache your credentials by running the following command:
`git config --global credential.helper osxkeychain`

## Git SSH

- First check for existing SSH keys on your computer by running: `ls -al ~/.ssh`
Lists the files in your .ssh directory, if they exist

- Check the directory listing to see if you have files named either `id_rsa.pub` or `id_dsa.pub`. If you don't have either of those files then read on, otherwise skip the next section.
- If you don't have an SSH key you need to generate one. To do that you need to run the commands below, and make sure to substitute the placeholder with your email. The default settings are preferred, so when you're asked to enter a file in which to save the key, just press Enter to continue.
- enter this command: `ssh-keygen -t rsa -C "stevan.pataki.1999@gmail.com"`
- Run the following commands to add your SSH key to the `ssh-agent`: `eval "$(ssh-agent -s)"`
- If you're running macOS Sierra 10.12.2 or later, you will need to modify your `~/.ssh/config` file to automatically load keys into the ssh-agent and store passphrases in your keychain:
`Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa`
  
 - No matter what operating system version you run you need to run this command to complete this step: `ssh-add -K ~/.ssh/id_rsa`
 - The last step is to let GitHub know about your SSH key so GitHub can recognize you. Run this command to copy your key to your clipboard: `pbcopy < ~/.ssh/id_rsa.pub`
 - Then go to GitHub and input your new SSH key. Paste your key in the "Key" text-box and pick a name that represents the computer you're currently using.

We are now ready to use SSH with GitHub!

# VSCode setup

Login to Github via VSCode Sync to skip or speed up the process or if you want to setup VSCode manually follow instructions below.

- Download this extensions: 
  - Font `https://www.jetbrains.com/lp/mono/` - Set font to: `JetBrains Mono` and font size to `14px`
  - Or run two brew commands: `brew tap homebrew/cask-fonts` and `brew install font-jetbrains-mono`
  - Sublime Matirial theme `jprestidge.theme-material-theme` - Set theme to: `Sublime Matirial theme Dark`
  - (Alternative) Sublime Matirial theme `github.github-vscode-theme` - Set theme to: `GitHub Dark`
  - Material Icon Theme `pkief.material-icon-theme` - Set icon theme to: `Material Icon Theme`
  - Better Comments `aaron-bond.better-comments`
  - Bracket Pair Colorizer `coenraads.bracket-pair-colorizer`
  - Colorize `kamikillerto.vscode-colorize`
  - GitLense `eamodio.gitlens`
  - Highlight Matching Tag `vincaslt.highlight-matching-tag`
  - Import Cost `wix.vscode-import-cost`
  - Open in browser `techer.open-in-browser`
  - Error Lens `usernamehw.errorlens`
  
- Install other extension if needed for specific dev setup

## VSCode settings JSON:

``` 
{
    "workbench.iconTheme": "material-icon-theme",
    "workbench.colorTheme": "GitHub Dark",
    "editor.fontFamily": "'JetBrains Mono', Menlo, Monaco, 'Courier New', monospace",
    "editor.fontSize": 14,
    "errorLens.severityText": [
        "ERROR",
        "WARNING"
    ],
    "editor.minimap.enabled": false
}
```

# Last Steps

- Launch all programs and configure them
- Setup Dock, Menubar, Desktop, Finder, Launchpad if you didn't do that earlier
- After that restart Macbook to apply some changes that maybe need a restart
- This is the end of the basic setup
- Below are guidelines for installing specific dev environments that i use the most currently (like fullstack setup with Nodejs/React or MySql/PostgresSql setups )

You are Done!

# DEV Environments setups

**Below are setups for specific dev environments setups that i currently use the most some that i use currently for work or uni or i dont use that often are writen in Notion in notebook labelled as** ***Instalation Handbooks*** 

# IDE's

Install JetBrains IDE's for needed development workflows

IDE's to install via jetbrains toolbox:
  - WebStorm
  - DataGrip

# NodeJS (Backend)

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine.

## Install nvm

Nvm is short for node-version-manager it is used to install and manage multiple node versions

install nvm by running this command:
`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash`

Follow any directions as stated by the installer (e.g. editing the `~/.zshrc file`).

## Install Node via nvm

Install most recent NodeJS version via nvm by running this command:

`nvm install node`

Or install specific node version (in this case node 16) by running this command:
`nvm install 16`

### Yarn

Install yarn by running this command: `npm install -g yarn`

### TypeScript

Install Typescript compailer by running this command: `npm install -g typescript`

### NestJS

Install nest cli by running this command: `npm install -g @nestjs/cli`

# Docker Desktop (Backend)

Install docker-desktop by running this command: `brew install --cask docker`

After installation launch Docker Desktop and configure settings.
