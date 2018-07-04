# Create Embark DApp

The easiest way to create Ethereum [DApps](https://en.wikipedia.org/wiki/Decentralized_application) thanks to [Embark](https://embark.status.im/).

- [Getting Started](#getting-started) — How to create a DApp
- [Starting from Templates](#starting-from-templates) — How to create a DApp from an Embark template

If you run into any issues or have feedback, please [file an issue](https://github.com/michaelsbradleyjr/create-embark-dapp/issues/new).

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

Out of the box, we get:

- great stuff
- and other cool stuff too

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

Invoke [Embark commands](https://embark.status.im/docs/embark_commands.html).<br>
For example `npm run dev` could instead be `npm run embark run`.

## Starting from Templates

There are templates in the [Embark repo](https://github.com/embark-framework/embark/tree/develop/templates/) (the list will be growing!) that you can use to bootstrap your DApp.

To use a template:

1.  Go to https://embark.status.im/create-embark-dapp#templates
2.  Search for a template you want and get its name (looks like `basic-contracts`)
3.  Run: `create-embark-dapp another-dapp --template basic-contracts`
4.  Done 💥

### `boilerplate`

When the `--template` flag is not supplied, and neither [`--demo`](#--demo) nor [`--simple`](#--simple) is used, it's equivalent to indicating `--template boilerplate`.

**Note:** &nbsp; it is *incorrect* to use the `--template` flag while *also* specifying `--demo` and/or `--simple`. Likewise, it is incorrect to specify both `--demo` and `--simple`.

### `--tree`

To use a specific revision of the Embark codebase (and so a template as found in that revision), indicate a [tree-ish](https://git-scm.com/docs/gitglossary#gitglossary-aiddeftree-ishatree-ishalsotreeish) that's valid with respect to the [Embark repository](https://github.com/embark-framework/embark).

```shell
create-embark-dapp my-dapp \
                   --template demo \
                   --tree some-feature-branch
```

When the `--tree` flag is not used, templates will be extracted from the most recent version of the Embark package as can be determined with `npm show embark version`.

**Note:** &nbsp; it is *incorrect* to use this flag without supplying a value, as it assumes no default value.

The `--tree` flag may be used with or without the `--template` flag, and may be used in conjunction with other flags.

### `--embark-version`

To override the version of Embark specified in a template's `package.json`, indicate a [dependency value](https://docs.npmjs.com/files/package.json#dependencies) (version number or range, URL, path, etc.) that's valid for Embark.

```shell
create-embark-dapp my-dapp \
                   --template showcase-xyz \
                   --tree new-templates-wip
                   --embark-version 3.1.4
```

**Note:** &nbsp; it is *incorrect* to use this flag without supplying a value, as it assumes no default value.

The `--embark-version` flag may be used with or without the `--template` flag, and may be used in conjunction with other flags except `--embark-version-as-tree`.

### `--embark-version-as-tree`

Use the `--embark-version-as-tree` flag to have the `--embark-version` flag automatically derive its value from the `--tree` flag's value.

The following are equivalent:

``` shell
create-embark-dapp my-dapp \
                   --template demo \
                   --tree some-feature-branch \
                   --embark-version-as-tree
```
``` shell
create-embark-dapp my-dapp \
                   --template demo
                   --tree some-feature-branch \
                   --embark-version 'embark-framework/embark#some-feature-branch'
```

**Note:** &nbsp; it is *incorrect* to supply a value for this flag. Likewise, it is incorrect to specify both `--embark-version` and `--embark-version-as-tree`.

The `--embark-version-as-tree` flag may be used with or without the `--template` flag, and may be used in conjunction with other flags except `--embark-version`.

## Acknowledgements

We are grateful to the authors of existing open source projects for the inspiration they provided:

- [Create Next App](https://github.com/segmentio/create-next-app)
- [Create React App](https://github.com/facebook/create-react-app)

Looking for alternatives? Here are some other Ethereum dev kits:

- [Truffle](https://github.com/trufflesuite/truffle)

Questions? Feedback? [Please let us know](https://github.com/michaelsbradleyjr/create-embark-dapp/issues/new).
