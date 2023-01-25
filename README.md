# Mac Lab Dev Setup Instructions
Instructions for creating Dev Accounts on our Mac Workstations


*REF: https://mac.install.guide/commandlinetools/index.html

# Xcode CLI Tools
`xcode-select –-install`


# Homebrew

`$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)”`


```bash
==> Next steps:
- Run these three commands in your terminal to add Homebrew to your PATH:
    echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/servicewths/.zprofile
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/servicewths/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
- Run brew help to get started
- Further documentation:
    https://docs.brew.sh
```

# Ruby
## Use Chruby
https://mac.install.guide/ruby/12.html

`brew install ruby-install chruby`

```bash
==> chruby
Add the following to the ~/.bash_profile or ~/.zshrc file:
  source /opt/homebrew/opt/chruby/share/chruby/chruby.sh

To enable auto-switching of Rubies specified by .ruby-version files,
add the following to ~/.bash_profile or ~/.zshrc:
  source /opt/homebrew/opt/chruby/share/chruby/auto.sh

```

### add to terminal:
touch ~/.zshrc  
open -e ~/.zshrc

 - Paste 
source /opt/homebrew/opt/chruby/share/chruby/chruby.sh
source /opt/homebrew/opt/chruby/share/chruby/auto.sh
chruby ruby-3.2.0
 - Save
 - Refresh zsh
exec zsh

### Install Ruby

`ruby-install -U`

# Python
Brew install python

## Install pipenv
`sudo -H pip3 install -U pipenv`


