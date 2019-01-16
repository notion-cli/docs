---
title: Understanding Notion
---

# Understanding Notion


## Tools and Toolchains

Notion's job is to manage your JavaScript command-line tools, such as `node`, `npm`, `yarn`, or executables shipped as part of JavaScript packages.

Similar to package managers, Notion keeps track of which project (if any) you're working on based on your current directory. Notion automatically manages a separate _toolchain_—a set of tools and their versions—for each project, as well as a global _user toolchain_ for your personal use.

By keeping toolchains separate, Notion ensures that a tool installed in one toolchain doesn't "bleed" into another where it isn't installed. This lets you use whatever Node-based tools you like for personal use, without worrying that they'll affect your project scripts.

## User Toolchain

Usually, once you've got Notion installed, you'll want to pick a version of Node for personal use. Most developers like to stick to a recent version, so you can leave the version unspecified and Notion will install the latest release:

```bash
$ notion install node
```

If you like using the [Yarn](https://yarnpkg.com) package manager, you can also install a recent version of that into your toolchain:

```bash
$ notion install yarn
```

### Installing other tools into the user toolchain

{% include warn.html content="This feature is in development." %}

With `notion install`, you can also install command-line tools that are distributed via npm into your user toolchain.

```bash
# install the `ember` executable from the `ember-cli` package
$ notion install ember-cli

# install the `vuepress` executable
$ notion install vuepress
```

Now each of these tools is available for your personal use, just by calling them directly:

```bash
# create a new Ember app
$ ember new my-app

# run a Vuepress development server
$ echo '# Hello World' > README.md
$ vuepress dev
```

## Project Toolchains

Notion allows a team or community of collaborators to standardize on the development tools they use for their project.

The `notion pin` command allows you to choose your Node or package manager version for a project:

```bash
$ notion pin node 10.3
```

Notion stores this in your `package.json` so you can commit your choice of tools to version control:

```bash
$ grep -A 2 toolchain package.json
  "toolchain": {
      "node": "10.3.0"
  }
```

This way, everyone who uses Notion to work on the project automatically gets the same version you selected:

```bash
$ node --version
10.3.0
```
