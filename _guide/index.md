---
title: Introduction
---

# Introduction

Welcome to Notion!

Notion is a hassle-free way to manage your JavaScript command-line tools.

## Features

- Speed 🚀
- Seamless, per-project version switching
- Cross-platform support, including Windows and all Unix shells
- Support for multiple package managers
- Stable tool installation—no reinstalling on every Node upgrade!
- Extensibility hooks for site-specific customization


## Why Notion?

Notion's job is to get out of your way.

With Notion, you can select a Node engine once and then stop worrying about it. You can switch between projects and stop having to manually switch between Nodes. You can install npm binaries in your toolchain without having to constantly reinstall them or figure out why they've stopped working.

### Quickly set up and switch Node engines

With Notion, fetching and using a particular version of Node is a snap:
```sh
notion install node 11
```
You'll notice right away how responsive the tool is. Your development time is precious! You deserve tools that jump at your command.

### Reproducible environments for collaborators

Notion lets you choose your Node engine and package manager for a project once with a simple command:
```
notion pin node 10
```
Notion saves the precise version of the Node engine in your `package.json` so you can commit your selection to git. From that point on, every time you run Node inside your project directory, Notion _automatically_ switches to the precise version of Node you chose. Similarly, all your collaborators can do the same simply by installing Notion on their development machine.

### Install and forget

Notion also lets you install your favorite package binaries as command-line tools, without worrying about them interfering with your development projects. Even better, these tools get pinned to a particular Node engine at installation time and don't change unless you explicitly tell them to—no more surprise bitrot or constant reinstallation!
```sh
notion install surge
surge -h
```

## How does it work?

Notion does not use any fancy OS- or shell-specific hooks. It's built on the simple, battle-tested approach of shims.

Whenever you install a tool with Notion, it adds a shim to your `PATH` that acts as an intelligent (but fast!) router to the right version of the tool and runs it with the right Node engine.

Notion is easy to install and has no external dependencies because it's built in [Rust](https://www.rust-lang.org/) as a single, super-fast binary executable.
