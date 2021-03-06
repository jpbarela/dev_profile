# Profile

This repo contains some basic tools and a sample `.bash_profile` to help bootstrap new development environments.

## Homebrew
The basic package manager is [Homebrew](https://brew.sh/).

The installation script is 
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Git
### Completion
Completion is provided via Homebrew on Mac, `brew install git bash-completion`.  

### Editor
Changing the default editor to emacs, `git config --global core.editor "emacs"`

### GPG signing
1. Install gpg to generate a private key `brew install gpg`.
2. Create a new key `gpg --full-generate-key`.
3. Add the key to git `git config --global user.signingkey {SIGNING_KEY}`.
4. Install [GPGSuite](https://gpgtools.org/).
5. Install pin-entry to enable a prompt on `brew install pin-entry`
5. Update the git config `git config --global commit.gpgsign true`.

### SSH setup
1. Generate a new key `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
2. Update the `~/.ssh/config`
```bash
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
```
3. Add the key to ssh agent `ssh-add -K ~/.ssh/id_rsa`
4. Copy the key `pbcopy < ~/.ssh/id_rsa.pub`
5. Add it to github or another git repo

## Node 
The basic node environment manage is [nvm]()

The install script is `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash`

## Ruby 
The basic ruby environment manager is [rbenv](https://github.com/rbenv/rbenv). 

It is installed with brew `brew install rbenv`.

### Aliases
| alias | full command	|
| ----- | ------------- |
| be	| bundle exec	|