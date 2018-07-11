---
layout: post
title: "Managing a Multi-Python System with pyenv"
date: 2018-07-10
categories: python system macos
---

I ran into the need to have multiple versions of Python installed on my machine at one time - different ones for different projects. Thankfully, I'm not the only one with this need!

Enter [pyenv](https://github.com/pyenv/pyenv)

I won't bore you with the product details, you can go read those yourself (written by more qualified individuals).

# Setup
If you're on Macos, the setup is cake.

```shell
brew update

# initial installation
brew install pyenv

# update existing installation
brew upgrade pyenv
```

But beware! If you also use zsh, you may need to add ~/.pyenv to your `$PATH` if you want `python --version` to utilize the Python version specified by pyenv.

```shell
touch ~/.zsh.after/pyenv.zsh
echo '# add .pyenv to PATH' >> ~/.zsh.after/pyenv.zsh
echo 'export PATH="/Users/username/.pyenv:$PATH"' >> ~/.zsh.after/pyenv.zsh
echo 'eval "$(pyenv init -)"' >> ~/.zsh.after/pyenv.zsh
echo '' >> ~/.zsh.after/pyenv.zsh
```

_Note that you'll need to update `username` with your system's username._

# Usage

Now you're golden! Go play with your Python versions!

```shell
# view currently installed pyenv versions
pyenv versions

# view list of installable Python versions
pyenv install --list

# install specific Python version
pyenv install 3.7.0

# uninstall specific Python version
pyenv uninstall 2.6.9

# set local Python version
pyenv local 2.7.15

# unset local Python version
pyenv local --unset

# set global Python version
pyenv global 3.7.0
```
