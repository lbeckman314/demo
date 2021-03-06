# demo

This is the catch-all repo for the following projects:

## Overview

1) [demo-web](https://github.com/lbeckman314/demo-web): a minimal pseudo-terminal that can be embedded on a webpage. This is a web client for demo-server.
2) [demo-cli](https://github.com/lbeckman314/demo-cli): a CLI that allows you to run commands from the terminal. This is a go client for demo-server.
3) [demo-server](https://github.com/lbeckman314/demo-server): a server that runs custom-defined commands in a sandboxed environment. This is a Node.js server for demo-web and demo.go.
4) [demo-docs](https://github.com/lbeckman314/demo-docs): converts code blocks in runnable code samples that sccepts user input (via connecting to demo-server)!
5) [demonic](https://github.com/lbeckman314/demonic): an [xterm.js](https://xtermjs.org/) and [terminado](https://github.com/jupyter/terminado)-powered web-app that gives you all the powers of a terminal right in the browser. Acts as it's own client and server model. Like demo-web but more feature-rich and broadly-focused.

## Comparison

| Program                                                   | Function                   | Use if you want...                                                                        |
|-----------------------------------------------------------|----------------------------|-------------------------------------------------------------------------------------------|
| [demo-web](https://github.com/lbeckman314/demo-web)       | Web client                 | to embed a pseudo-terminal on a website or in online documentation.                       |
| [demo-cli](https://github.com/lbeckman314/demo-cli)         | Go client                  | to access sandboxed applications from the comfort of the command line.                    |
| [demo-server](https://github.com/lbeckman314/demo-server) | Node.js server             | to serve custom commands in a sandboxed environment to clients like demo-web and demo-cli. |
| [demo-docs](https://github.com/lbeckman314/demo-docs)     | Web docs                   | to convert code blocks into runnable blocks in HTML-ized markdown files.                  |
| [demonic](https://github.com/lbeckman314/demonic)         | Web client & Python server | a fully fleged terminal in the web that *also* runs sandboxed applications.               |

## FAQ's

- Why have separate project repositories (submodules) instead of one unified repository?

I'd like each project to be able to function independently, so that user's may be free to switch out clients and servers at their discretion. And developers or contributors should be able to fork or clone only the components they wish to extend or work on. This division between subprojects introduces some added complexity (e.g. submodules), but at least for this project, is balanced out by the added level of choice for users and developers.

- What's the difference between [demo-web](https://github.com/lbeckman314/demo-web), [demonic](http://github/lbeckman314/demonic), and [xterm.js](https://xtermjs.org/)/[terminado](https://github.com/jupyter/terminado)-?

**demo-web** is my own attempt at writing a web-based terminal. It aims to allow users to send code snippets and commands to a self-hosted server, from which they receive output from STDOUT. This model lets you define your own commands and have fine-grained control over the spawning, execution, and termination of those commands. It doesn't handle ASCII-escape sequences (yet!), so no vim or other terminal-specific features. Just plain old text.

**demonic** is a full web-based terminal/shell combo. This means you *can* run vim, tmux, lolcat, etc. with ease. It's powered by [xterm.js](https://xtermjs.org/) and [terminado](https://github.com/jupyter/terminado), which is are awesome projects written by talented groups of contributors and maintainers. For your own web-based terminal projects, those are good places to start. demonic simply leverages both xterm.js and terminado to serve a sandbox of some of my applications for people to try out without having to install them.

**xterm.js and terminado** are two separate but very cool projects. xterm.js is a "terminal for the web", and can be integrated into online or electron-based projects where a terminal can be used. terminado is a "Tornado websocket backend for the Xterm.js Javascript terminal emulator library" and as such serves the sandbox portion of demonic. 
