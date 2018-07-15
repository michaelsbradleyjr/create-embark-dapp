# Create Embark DApp

The easiest way to create Ethereum [DApps](https://en.wikipedia.org/wiki/Decentralized_application) thanks to [Embark](https://embark.status.im/).

- [Getting Started](#getting-started) — How to create a DApp
- [Starting from Templates](#starting-from-templates) — How to create a DApp from an Embark template

If you run into any issues or have feedback, please [file an issue](https://github.com/michaelsbradleyjr/create-embark-dapp/issues/new).

Updating this, experimenting with magithub and PR reviews, comments, etc.

## Overview

```shell
npm install -g create-embark-dapp

create-embark-dapp my-dapp
cd my-dapp/
npm run dev
```

Open [http://localhost:8000](http://localhost:8000) to view your running DApp.
<!--
<img width="600" alt="Create Embark DApp running in terminal" src="https://cloud.githubusercontent.com/assets/1026125/25556236/0ac91ca6-2cae-11e7-87ae-bb7974285063.png" />

<img width="600" alt="Create Embark DApp running in terminal" src="https://cloud.githubusercontent.com/assets/1026125/25556240/111fc3b6-2cae-11e7-84b6-961de4fd27f9.png" />
-->
### Start Coding Now

You **don't** have to install anything else &mdash; you can just start coding.

After running `create-embark-dapp`, you're good to go!

## Getting Started

### Installation

Install it once globally:

```shell
npm install -g create-embark-dapp
```

**You’ll need to have Node >= 8.11.3 LTS on your machine**. You can use [nvm](https://github.com/creationix/nvm#usage) to easily switch Node versions between different projects.

### Creating a DApp

To create a new DApp, run:

```shell
create-embark-dapp my-dapp
cd my-dapp
```

It will create a directory called `my-dapp` inside the current folder.<br>
Inside that directory, it will generate the initial project structure and install necessary dependencies:

```
my-dapp
  app/
    css/
    images/
    index.html
    js/
      index.js
  chains.json
  config/
    blockchain.js
    communication.js
    contracts.js
    development/
      genesis.json
      password
    namesystem.js
    storage.js
    testnet/
      password
    webserver.js
  contracts/
  embark.json
  package.json
  test/
    contract_spec.js
```

#### Out of the box, we get: :heart:

- automatic contract re/builds and re/deployments
- simple blockchain and contract management
- easy access to decentralized storage and communication
- integration with any web technologies and build pipelines your prefer

#### `--demo`

To create a demo Embark project with examples for working with contracts, IPFS, and Whisper, run:

```shell
create-embark-dapp my-dapp --demo
```

The `--demo` flag is an alias for `--template demo`.<br>
See [Starting from Templates](#starting-from-templates).

#### `--simple`

To create a barebones project meant only for contract development, run:

```shell
create-embark-dapp my-dapp --simple
```

The `--simple` flag is an alias for `--template simple`.<br>
See [Starting from Templates](#starting-from-templates).

### Running a DApp

Once the installation is finished, you can run some commands in your project:

#### `npm run dev`

Runs the DApp in development mode.<br>
Open [http://localhost:8000](http://localhost:8000) to view it in the browser.

#### `npm run embark <cmd>`

Invoke [Embark commands](https://embark.status.im/docs/embark_commands.html). For example:

``` shell
npm run embark build
```

:tada:&nbsp; Add a command alias to your shell to cut down on typing `npm run embark`.

If you're using `bash`, you could add the following to `~/.bashrc` and/or execute it at a `bash` prompt.

``` shell
alias embark='npm run embark'
```

Inside a DApp project directory `embark build` would then be equivalent to `npm run embark build`.

## Starting from Templates

There are templates in the [Embark repo](https://github.com/embark-framework/embark/tree/develop/templates/) (the list will be growing!) that you can use to bootstrap your DApp.

### `--template`

To use a template:

1.  Go to https://embark.status.im/create-embark-dapp#templates
2.  Search for a template you want and get its name (looks like `basic-contracts`)
3.  Run: `create-embark-dapp another-dapp --template basic-contracts`
4.  Done 💥

### `boilerplate`

When the `--template` flag is not used or no value is supplied, and neither [`--demo`](#--demo) nor [`--simple`](#--simple) is used, it's equivalent to indicating `--template boilerplate`.

**Note:** &nbsp; it is *incorrect* to use the `--template` flag while *also* using `--demo` and/or `--simple`. Likewise, it is incorrect to use both `--demo` and `--simple`.

### `--template-source`

To use a specific source for the template code, any npm [package specifier](https://docs.npmjs.com/cli/install#description) (URL, folder, gzipped tarball, etc.) may be supplied to the `--template-source` flag.

So if a user `ghuser` has forked Embark and has a branch named `my-templates`, the following could be run:

```shell
create-embark-dapp my-dapp \
                   --template-source 'ghuser/embark#my-templates'
```

The package will be fetched with `npm pack` and decompressed. The only expectation is that the extracted archive will have the following structure:

```
.
  package.json
  templates/
    <template-name>/
```

The extracted `package.json` will be ignored, but it must be present and valid per npm's [description of a package](https://docs.npmjs.com/cli/install#description).

When the `--template-source` flag is not used, it's equivalent to indicating `--template-source embark`.

The `--template-source` flag may be used with or without the `--template` flag, and may be used in conjunction with other flags.

### `--embark-version`

To override the version of Embark specified as a dependency in a template's `package.json`, indicate any npm [dependency value](https://docs.npmjs.com/files/package.json#dependencies) (version number or range, URL, path, etc.) that will be valid relative to `"dependencies": {"embark": "<value>"}`.

```shell
create-embark-dapp my-dapp \
                   --template showcase-feature \
                   --template-source 'embark-framework/embark#new-templates-wip'
                   --embark-version 'ghuser/embark#fix-feature'
```

**Note:** &nbsp; it is *incorrect* to use this flag without supplying a value.

The `--embark-version` flag may be used with or without the `--template` flag, and may be used in conjunction with other flags.

## Acknowledgements

We are grateful to the authors of existing open source projects for the inspiration they provided:

- [Create Next App](https://github.com/segmentio/create-next-app)
- [Create React App](https://github.com/facebook/create-react-app)

Looking for alternatives? Here are some other Ethereum dev kits:

- [Truffle](https://github.com/trufflesuite/truffle)

Questions? Feedback? [Please let us know](https://github.com/michaelsbradleyjr/create-embark-dapp/issues/new).
