---
title: Features
---

### Flag/Argument parsing

No CLI framework would be complete without a flag parser. We've built a custom one from years of experimentation that we feel consistently handles user input flexible enough for the user to be able to easily use the CLI in ways they expect, but without compromising strictness guarantees to the developer.

### Configurable Topic Separators

By default topics will be separated with colons, e.g. `my:awesome:command`. However, you have the option to use spaces if you prefer, e.g. `my awesome command`.

### Super Speed

The overhead for running an oclif CLI command is almost nothing. [It requires very few dependencies](https://www.npmjs.com/package/@oclif/core?activeTab=dependencies) (only 35 dependencies in a minimal setup—including all transitive dependencies). Also, only the command to be executed will be required with node. So large CLIs with many commands will load just as fast as a small one with a single command.

### CLI Generator

Run a single command to scaffold out a fully functional CLI and get started quickly. See [Usage](#-usage) below.

### Testing Helpers

We've put a lot of work into making commands easily testable and easy to mock out stdout/stderr. The generator will automatically create [scaffolded tests](https://github.com/oclif/hello-world/blob/main/test/commands/hello/world.test.ts).

### Auto-documentation

By default you can pass `--help` to the CLI to get help such as flag options and argument information. This information is also automatically placed in the README whenever the npm package of the CLI is published. See the [hello-world CLI example](https://github.com/oclif/hello-world)

### Plugins

Using plugins, users of the CLI can extend it with new functionality, a CLI can be split into modular components, and functionality can be shared amongst multiple CLIs. See [Building your own plugin](#-building-your-own-plugin) below.

### Hooks

Use lifecycle hooks to run functionality any time a CLI starts, or on custom triggers. Use this whenever custom functionality needs to be shared between various components of the CLI.

### JSON Output

You can opt-in to using the `--json` flag which will automatically supress console logs and display the final result of the command as valid JSON output. This is very useful if you want your CLI to be used for scripting in CI/CD environments.

### TypeScript (or not)

Everything in the core of oclif is written in TypeScript and the generator can build fully configured TypeScript CLIs or just plain JavaScript CLIs. By virtue of static properties in TypeScript the syntax is a bit cleaner in TypeScript—but everything will work no matter which language you choose. If you use plugins support, the CLI will automatically use `ts-node` to run the plugins making it easy and fast to use TypeScript with minimal-to-no boilerplate needed for any oclif CLI.

### Auto-updating Installers

oclif can package your CLI into [different installers](releasing.md) that will not require the user to already have node installed on the machine. These can be made auto-updatable by using [plugin-update](https://github.com/oclif/plugin-update).

### Autocomplete

Include terminal autocompletion for your CLI via [plugin-autocomplete](https://github.com/oclif/plugin-autocomplete). Once installed, users can complete command names and flag names.

```bash
$ my-cli p<tab><tab> # will list all commands starting with 'p' for completion
```
