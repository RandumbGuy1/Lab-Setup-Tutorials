# Mac Lab Dev Environments
Instructions for creating local development environments on a Mac Workstation.

*Reference: https://mac.install.guide/commandlinetools/index.html

## Creating a local dev account
Before you can configure your local development environments you first must make an account with admin privileges. This is a **WORK** computer, not a home computer. All usage with these machines must be for professional/academic purposes only.

1. Log into your workstation with the administrative account.
2. Open Settings/Users
3. Create a new Account 
   - Username convention: Use your first name, last initial. e.g.: "Jeff L"
   - Use a strong password that you will remember
   - Select an emoji/memoji for your account
   - Ensure the account type is "Admin"
   - Avoid: Nicknames and Custom Avatars

## Dependancies
These packages should be installed first for all users.

### Install Xcode Command Line Tools
Xcode is an IDE for iOS. The command line tools allow you to install homebrew (The defacto package manager for the Mac). This may already be installed globally.

1. Open a terminal.
2. Check if Xcode CLT is already installed:
```zsh
xcode-select --version
```

3. If not installed, install with the following command:
```zsh
xcode-select --install
```

### Install Homebrew
Homebrew is a popular package manger for the MacOS

1. Open a terminal.
2. Check if Homebrew is already installed:
```zsh
brew --version
```

3. If not installed, install with the following command:
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installing, you'll see something like the following message. 
1. Copy the three lines "echo," "echo," and "eval" from your terminal. 
2. Then paste and run. 
3. **DO NOT PASTE THE CODE BELOW** Your paths will be different than what you see here. 
4. Instead *read your terminal* and follow those instructions.
```zsh
    ==> Next steps:
    - Run these three commands in your terminal to add Homebrew to your PATH:
        echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/<USER_NAME>/.zprofile
        echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<USER_NAME>/.zprofile
        eval "$(/opt/homebrew/bin/brew shellenv)"
    - Run brew help to get started
    - Further documentation:
        https://docs.brew.sh
```

## Dev Environments

## Ruby
Ruby is used by the MacOS so it's important to use a Ruby Version Manager. Jekyll's documentation recomends using chruby so that's what we will use.

*Reference: https://mac.install.guide/ruby/12.html

```zsh
brew install ruby-install chruby
```

After installing, you'll see the following instructions in the terminal
```bash
==> chruby
Add the following to the ~/.bash_profile or ~/.zshrc file:
  source /opt/homebrew/opt/chruby/share/chruby/chruby.sh

To enable auto-switching of Rubies specified by .ruby-version files,
add the following to ~/.bash_profile or ~/.zshrc:
  source /opt/homebrew/opt/chruby/share/chruby/auto.sh

```

#### Add chruby to your terminal path

Create a zsh terminal profile file if you do not already have one
```zsh
touch ~/.zshrc  
```

Open the file in Text Edit
```zsh
open -e ~/.zshrc
```

Paste the following source paths
```text
source /opt/homebrew/opt/chruby/share/chruby/chruby.sh
source /opt/homebrew/opt/chruby/share/chruby/auto.sh
chruby ruby-3.2.0
```

After pasting, save the file, then go back to terminal.

You can refresh your terminal with the following command. This will reload terminal with your profile paths

```zsh
exec zsh
```

#### Installing Latest Ruby

Finall, install the latest version of Ruby
```zsh
ruby-install ruby
```

*Note: If running Ruby 3.2 and recieving an error called "tainted?": update liquid
`bundle update liquid`

## Python
Download the latest version of Python and install manually

- https://www.python.org/

### Installing pipenv
```zsh
sudo -H pip3 install -U pipenv
```

## Utilities

### VSCode Shortcut 
The Mac version of VSCode doesn't include the finder option "Open in VSCode." You can create a similar shortcut using Automator. The following stack overflow answer contains steps to accomplish this.

[Open a folder in vscode through Finder in macOS?](https://stackoverflow.com/a/70512321/7799574 "Best Answer IMHO")
