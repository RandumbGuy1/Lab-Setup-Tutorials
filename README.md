# Mac Lab Dev Setup Instructions
Instructions for creating Dev Accounts on our Mac Workstations

*Reference: https://mac.install.guide/commandlinetools/index.html

## Create a local account
* See instructor for these instructions

## Install Xcode Command Line Tools
```zsh
xcode-select --install
```

## Install Homebrew

First, install directly from the source
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)”
```

After installing, you'll see something like the following message. Copy the three lines that begin with "echo," "echo," and "eval" from your terminal. Then paste and run. Your paths will be different than what you see here.

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

## Installing Ruby
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

### Add chruby to your terminal path

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

### Installing Latest Ruby

Finall, install the latest version of Ruby
```zsh
ruby-install ruby
```

*Note: If running Ruby 3.2 and recieving an error called "tainted?": update liquid
`bundle update liquid`

## Installing Python
Download the latest version of Python and install manually

- https://www.python.org/

### Installing pipenv
```zsh
sudo -H pip3 install -U pipenv
```


