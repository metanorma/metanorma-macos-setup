Metanorma macOS Setup
======
[![Build Status](https://circleci.com/gh/riboseinc/metanorma-macos-setup/laptop.svg)](https://circleci.com/gh/riboseinc/metanorma-macos-setup)

The `metanorma-setup` script is used to setup a macOS computer for the
Metanorma publication workflow.

It is based on the [Laptop script](https://github.com/18F/laptop).

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* [macOS Sierra (10.12)](https://www.apple.com/osx/)
* macOS El Capitan (10.11)

Older versions may work but aren't regularly tested.

Install
-------

Run this command in your macOS Terminal:

```sh
bash <(curl -s https://raw.githubusercontent.com/riboseinc/metanorma-macos-setup/master/metanorma-setup)
```

Note that the script will ask you to enter your macOS password at various
points. This is the same password that you use to log in to your Mac.

**Once the script is done, make sure to quit and relaunch Terminal.**

It is highly recommended to run the script regularly to keep your computer
up to date. Once the script has been installed, you'll be able to run it
at your convenience by typing `metanorma-setup` and hitting `return` in your Terminal.

Debugging
---------

Your most recent `metanorma-setup` run will be saved to `~/metanorma-setup.log`. Read through it to see if
you can debug the issue yourself. If not, copy and paste the entire log into a
[new GitHub Issue](https://github.com/riboseinc/metanorma-macos-setup/issues/new) for us.


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
[nvm]: https://github.com/creationix/nvm
[puppeteer]: https://github.com/GoogleChrome/puppeteer
[Ruby]: https://www.ruby-lang.org/en/
[ruby-install]: https://github.com/postmodern/ruby-install
[Sublime Text 3]: http://www.sublimetext.com/3

It should take less than 15 minutes to install (depends on your machine and
internet connection).

Credits
-------

The metanorma-setup script is based on:

* [18F's Laptop](https://github.com/18F/laptop) script (CC0 licensed)
* [thoughtbot's laptop](https://github.com/thoughtbot/laptop) script (MIT licensed)
