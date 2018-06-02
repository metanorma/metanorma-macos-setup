Metanorma macOS Setup
======
[![Build Status](https://circleci.com/gh/riboseinc/metanorma-macos-setup/laptop.svg)](https://circleci.com/gh/riboseinc/metanorma-macos-setup)

The `metanorma-setup` script is used to setup a macOS computer for the
Metanorma publication workflow.

It is based on https://github.com/18F/laptop
Laptop is a script to set up an macOS computer for web development, and to keep
it up to date.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* [macOS Sierra (10.12)](https://www.apple.com/osx/)
* macOS El Capitan (10.11)
* macOS Yosemite (10.10)
* macOS Mavericks (10.9)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Begin by opening the Terminal application on your Mac. The easiest way to open
an application in macOS is to search for it via [Spotlight]. The default
keyboard shortcut for invoking Spotlight is `command-Space`. Once Spotlight
is up, just start typing the first few letters of the app you are looking for,
and once it appears, press `return` to launch it.

In your Terminal window, copy and paste the command below, then press `return`.

```sh
bash <(curl -s https://raw.githubusercontent.com/riboseinc/metanorma-macos-setup/master/metanorma-setup)
```
The [script](https://github.com/riboseinc/metanorma-macos-setup/blob/master/mac) itself is
available in this repo for you to review if you want to see what it does
and how it works.

Note that the script will ask you to enter your macOS password at various
points. This is the same password that you use to log in to your Mac.
If you don't already have it installed, GitHub for Mac will launch
automatically at the end of the script so you can set up everything you'll
need to push code to GitHub.

**Once the script is done, make sure to quit and relaunch Terminal.**

More [detailed instructions with a video][video] are available in the Wiki.

It is highly recommended to run the script regularly to keep your computer
up to date. Once the script has been installed, you'll be able to run it
at your convenience by typing `laptop` and hitting `return` in your Terminal.

[Spotlight]: https://support.apple.com/en-us/HT204014
[video]: https://github.com/riboseinc/metanorma-macos-setup/wiki/Detailed-installation-instructions-with-video

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`. Read through it to see if
you can debug the issue yourself. If not, copy and paste the entire log into a
[new GitHub Issue](https://github.com/riboseinc/metanorma-macos-setup/issues/new) for us.

#### Git Seekrets False Positives

Sometimes the `git-seekrets` rules may indicate a false positive and match
things that aren't actually secrets. This can happen if the regular
expressions used to `match` and `unmatch` are too strict.

Make sure you have [the latest rulesets from this repository by running the
git-seekrets installation script](#want-to-install-just-git-seekret).

If the ruleset is still triggering a false positive, please open an issue
(or a pull request if you know how to fix the regular expression), and
include the text that is being treated as a false positive, along with the
rules installed on your computer. Please run this command to output
your current rules, then copy and paste them into the GitHub issue:

```shell
cat ~/.git-support/seekret-rules/*.rule
```

What it sets up
---------------

* [chruby] for managing [Ruby] versions
* [Homebrew] for managing operating system libraries
* [Homebrew Cask] for quickly installing Mac apps from the command line
* [nvm] for managing Node.js versions if you do not have [Node.js] already installed (Includes latest [Node.js] and [NPM], for running apps and installing JavaScript packages)
* [puppeteer] for running Headless Chrome via Node.js (used to generate PDFs from HTML)
* [ruby-install] for installing different versions of Ruby
* [Sublime Text 3] for coding all the things

[Bundler]: http://bundler.io/
[chruby]: https://github.com/postmodern/chruby
[Homebrew]: http://brew.sh/
[Homebrew Cask]: http://caskroom.io/
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[puppeteer]: https://github.com/GoogleChrome/puppeteer
[Ruby]: https://www.ruby-lang.org/en/
[ruby-install]: https://github.com/postmodern/ruby-install
[Sublime Text 3]: http://www.sublimetext.com/3

It should take less than 15 minutes to install (depends on your machine and
internet connection).

Customize in `~/.laptop.local` and `~/Brewfile.local`
-----------------------------------------------------

Your `~/.laptop.local` is run at the end of the `mac` script.
Put your customizations there. If you want to install additional
tools or Mac apps with Homebrew, add them to your `~/Brewfile.local`.
This repo already contains a [.laptop.local] and [Brewfile.local]
you can use to get started.

```sh
# Go to your macOS user's root directory
cd ~

# Download the sample files to your computer
curl --remote-name https://raw.githubusercontent.com/riboseinc/metanorma-macos-setup/master/.laptop.local
curl --remote-name https://raw.githubusercontent.com/riboseinc/metanorma-macos-setup/master/Brewfile.local
```

It lets you install the following tools and apps:

* [Atom] - GitHub's open source text editor
* [Exuberant Ctags] for indexing files for vim tab completion
* [Firefox] for testing your website on a browser other than Chrome
* [iTerm2] - an awesome replacement for the macOS Terminal
* [reattach-to-user-namespace] to allow copy and paste from Tmux
* [Tmux] for saving project state and switching between projects
* [Vim] for those who prefer the command line
* [Spectacle] - automatic window manipulation

[.laptop.local]: https://github.com/riboseinc/metanorma-macos-setup/blob/master/.laptop.local
[Brewfile.local]: https://github.com/riboseinc/metanorma-macos-setup/blob/master/Brewfile.local

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo` and `gem_install_or_update` can be used
in your `~/.laptop.local`.

Credits
-------

The 18F laptop script is based on and inspired by
[thoughtbot's laptop](https://github.com/thoughtbot/laptop) script.

### Public domain

thoughtbot's original work remains covered under an [MIT License](https://github.com/thoughtbot/laptop/blob/c997c4fb5a986b22d6c53214d8f219600a4561ee/LICENSE).

18F's work on this project is in the worldwide [public domain](LICENSE.md), as are contributions to our project.
