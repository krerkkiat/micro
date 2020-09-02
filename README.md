你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# ![Micro](./assets/logo.png)

[![Build Status](https://travis-ci.org/zyedidia/micro.svg?branch=master)](https://travis-ci.org/zyedidia/micro)
[![Go Report Card](https://goreportcard.com/badge/github.com/zyedidia/micro)](https://goreportcard.com/report/github.com/zyedidia/micro)
[![Join the chat at https://gitter.im/zyedidia/micro](https://badges.gitter.im/zyedidia/micro.svg)](https://gitter.im/zyedidia/micro?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/zyedidia/micro/blob/master/LICENSE)
[![Snap Status](https://build.snapcraft.io/badge/zyedidia/micro.svg)](https://build.snapcraft.io/user/zyedidia/micro)

Micro is a terminal-based text editor that aims to be easy to use and intuitive, while also taking advantage of the full capabilities
of modern terminals. It comes as one single, batteries-included, static binary with no dependencies, and you can download and use it right now.

As the name indicates, micro aims to be somewhat of a successor to the nano editor by being easy to install and use in a pinch, but micro also aims to be
enjoyable to use full time, whether you work in the terminal because you prefer it (like me), or because you need to (over ssh).

Here is a picture of micro editing its source code.

![Screenshot](./assets/micro-solarized.png)

To see more screenshots of micro, showcasing all of the default colorschemes, see [here](http://zbyedidia.webfactional.com/micro/screenshots.html).
 
You can also check out the website for Micro at https://micro-editor.github.io.

# Table of Contents
- [Features](#features)
- [Installation](#installation)
  - [Prebuilt binaries](#prebuilt-binaries)
  - [Package Managers](#package-managers)
  - [Building from source](#building-from-source)
  - [MacOS terminal](#macos-terminal)
  - [Linux clipboard support](#linux-clipboard-support)
  - [Colors and syntax highlighting](#colors-and-syntax-highlighting)
  - [Plan9, Cygwin](#plan9-cygwin)
- [Usage](#usage)
- [Documentation and Help](#documentation-and-help)
- [Contributing](#contributing)

- - -

# Features

* Easy to use and to install
* No dependencies or external files are needed -- just the binary you can download further down the page
* Multiple cursors
* Common keybindings (ctrl-s, ctrl-c, ctrl-v, ctrl-z...)
    * Keybindings can be rebound to your liking
* Sane defaults
    * You shouldn't have to configure much out of the box (and it is extremely easy to configure)
* Splits and tabs
* Nano-like menu to help you remember the keybindings
* Extremely good mouse support
    * This means mouse dragging to create a selection, double click to select by word, and triple click to select by line
* Cross platform (It should work on all the platforms Go runs on)
    * Note that while Windows is supported Mingw/Cygwin is not (see below)
* Plugin system (plugins are written in Lua)
* Persistent undo
* Automatic linting and error notifications
* Syntax highlighting (for over [120 languages](runtime/syntax)!)
* Colorscheme support
    * By default, micro comes with 16, 256, and true color themes.
* True color support (set the `MICRO_TRUECOLOR` environment variable to 1 to enable it)
* Copy and paste with the system clipboard
* Small and simple
* Easily configurable
* Macros
* Common editor things such as undo/redo, line numbers, Unicode support, softwrap...

# Installation

To install micro, you can download a [prebuilt binary](https://github.com/zyedidia/micro/releases), or you can build it from source.

If you want more information about ways to install micro, see this [wiki page](https://github.com/zyedidia/micro/wiki/Installing-Micro).

### Prebuilt binaries

All you need to install micro is one file, the binary itself. It's as simple as that!

Download the binary from the [releases](https://github.com/zyedidia/micro/releases) page.

On that page you'll see the nightly release, which contains binaries for micro which are built every night,
and you'll see all the stable releases with the corresponding binaries.

If you'd like to see more information after installing micro, run `micro -version`.

### Installation script

There is a great script which can install micro for you by downloading the latest prebuilt binary. You can find it at https://getmic.ro (the github repo for it is [here](https://github.com/benweissmann/getmic.ro)).

Then you can easily install micro:

    $ curl https://getmic.ro | bash

The script will install the micro binary to the current directory.

See the [Github page](https://github.com/benweissmann/getmic.ro) for more information.

### Package managers

You can install micro using Homebrew on Mac:

```
brew install micro
```

On Debian Linux, you can install micro through [snap](https://snapcraft.io/docs/core/install)

```
snap install micro --classic
```

Homebrew and snap are the two "officially" maintained package manager distributions of micro.

Micro is also available through other package managers on Linux such as AUR, Nix, and package managers
for other operating systems:

* Windows: [Chocolatey](https://chocolatey.org) and [Scoop](https://github.com/lukesampson/scoop)
    * `choco install micro`
    * `scoop install micro`
* OpenBSD: Available in the ports tree and also available as a binary package
    * `pkd_add -v micro`

### Building from source

If your operating system does not have a binary release, but does run Go, you can build from source.

Make sure that you have Go version 1.11 or greater and Go modules are enabled.

```
git clone https://github.com/zyedidia/micro
cd micro
make build
sudo mv micro /usr/local/bin # optional
```

The binary will be placed in the current directory and can be moved to
anywhere you like (for example `/usr/local/bin`).

The command `make install` will install the binary to `$GOPATH/bin` or `$GOBIN`.

You can install directly with `go get` (`go get github.com/zyedidia/micro/cmd/micro`) but this isn't
recommended because it doesn't build micro with version information, and doesn't disable debug mode.

### MacOS terminal

If you are using MacOS, you should consider using [iTerm2](http://iterm2.com/) instead of the default Mac terminal. The iTerm2 terminal has much better mouse support as well as better handling of key events. For best keybinding behavior, choose `xterm defaults` under `Preferences->Profiles->Keys->Load Preset`. The newest versions also support true color.

### Linux clipboard support

On Linux, clipboard support requires the 'xclip' or 'xsel' commands to be installed.

For Ubuntu:

```sh
sudo apt-get install xclip
```

If you don't have xclip or xsel, micro will use an internal clipboard for copy and paste, but it won't work with external applications.

### Colors and syntax highlighting

If you open micro and it doesn't seem like syntax highlighting is working, this is probably because
you are using a terminal which does not support 256 colors. Try changing the colorscheme to `simple`
by pressing CtrlE in micro and typing `set colorscheme simple`.

If you are using the default Ubuntu terminal, to enable 256 make sure your `TERM` variable is set
to `xterm-256color`.

Many of the Windows terminals don't support more than 16 colors, which means
that micro's default colorscheme won't look very good. You can either set
the colorscheme to `simple`, or download a better terminal emulator, like
mintty.

### Plan9, Cygwin, Mingw

These platforms are unfortunately not supported.

Micro uses the amazing [tcell library](https://github.com/gdamore/tcell), but this
means that micro is restricted to the platforms tcell supports. As a result, micro does not support
Plan9, and Cygwin (although this may change in the future). Micro also doesn't support NaCl (but NaCl is deprecated anyways).

# Usage

Once you have built the editor, simply start it by running `micro path/to/file.txt` or simply `micro` to open an empty buffer.

Micro also supports creating buffers from `stdin`:

```sh
ifconfig | micro
```

You can move the cursor around with the arrow keys and mouse.

You can also use the mouse to manipulate the text. Simply clicking and dragging
will select text. You can also double click to enable word selection, and triple
click to enable line selection.

# Documentation and Help

Micro has a built-in help system which you can access by pressing `Ctrl-E` and typing `help`. Additionally, you can
view the help files here:

* [main help](https://github.com/zyedidia/micro/tree/master/runtime/help/help.md)
* [keybindings](https://github.com/zyedidia/micro/tree/master/runtime/help/keybindings.md)
* [commands](https://github.com/zyedidia/micro/tree/master/runtime/help/commands.md)
* [colors](https://github.com/zyedidia/micro/tree/master/runtime/help/colors.md)
* [options](https://github.com/zyedidia/micro/tree/master/runtime/help/options.md)
* [plugins](https://github.com/zyedidia/micro/tree/master/runtime/help/plugins.md)

I also recommend reading the [tutorial](https://github.com/zyedidia/micro/tree/master/runtime/help/tutorial.md) for
a brief introduction to the more powerful configuration features micro offers.

# Contributing

If you find any bugs, please report them! I am also happy to accept pull requests from anyone.

You can use the [GitHub issue tracker](https://github.com/zyedidia/micro/issues)
to report bugs, ask questions, or suggest new features.

For a more informal setting to discuss the editor, you can join the [Gitter chat](https://gitter.im/zyedidia/micro).
