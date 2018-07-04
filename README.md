# Create Embark DApp

The easiest way to create Ethereum [DApps](https://en.wikipedia.org/wiki/Decentralized_application) thanks to [Embark](https://embark.status.im/).

- [Getting Started](#getting-started) — How to create an app
- [Starting from Examples](#starting-from-templates) — How to create a DApp from an Embark template

If you run into any issues or have feedback, please [file an issue](https://github.com/segmentio/create-next-app/issues/new)

## Overview

```sh
npm install -g create-embark-dapp

create-embark-dapp my-dapp
cd my-dapp/
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view your running DApp.
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

```sh
npm install -g create-embark-dapp
```

**You’ll need to have Node >= 8.11.3 LTS on your machine**. You can use [nvm](https://github.com/creationix/nvm#usage) to easily switch Node versions between different projects.

### Creating a DApp

To create a new DApp, run:

```
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

```
create-embark-dapp --demo my-dapp
cd my-dapp
```

The `--demo` flag is an alias for `--template demo`.<br>
See [Starting from Templates](#starting-from-templates).

#### `--simple`

To create a barebones project meant only for contract development, run:

```
create-embark-dapp --simple my-dapp
cd my-dapp
```

The `--simple` flag is an alias for `--template simple`.<br>
See [Starting from Templates](#starting-from-templates).

### Running a DApp

Once the installation is finished, you can run some commands in your project:

#### `npm run dev`

Runs the DApp in development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

#### `npm run embark <cmd>`

Invoke [Embark commands](https://embark.status.im/docs/embark_commands.html).<br>
For example `npm run dev` could instead be `npm run embark run`.

## Starting from Templates

There are templates in the [Embark repo](https://github.com/embark-framework/embark/tree/develop/templates/) (the list will be growing!) that you can use to bootstrap your DApp.

To use a template:

1.  Go to https://embark.status.im/create-embark-dapp#templates
2.  Search for a template you want and get it's name (looks like `basic-contracts`)
3.  Run: `create-embark-dapp --template basic-contracts my-other-dapp`
4.  Done 💥

### `boilerplate`

When the `--template` flag is not supplied, and neither [`--demo`](#--demo) nor [`--simple`](#--simple) is used, it's equivalent to indicating `--template boilerplate`.

### `--tree`

To use a specific version of Embark (and templates pegged to that version), indicate a [tree-ish](https://git-scm.com/docs/gitglossary#gitglossary-aiddeftree-ishatree-ishalsotreeish) that's valid with respect to the [Embark repository](https://github.com/embark-framework/embark).

```
create-embark-dapp --tree 3.1.2 --template demo my-dapp
cd my-dapp
```

The `--tree` flag may be used with or without the `--template` flag, and may be used in conjunction with the [`--demo`](#--demo) and [`--simple`](#--simple) flags.

## Acknowledgements

We are grateful to the authors of existing open source projects for the inspiration they provided:

- [Create Next App](https://github.com/segmentio/create-next-app)
- [Create React App](https://github.com/facebook/create-react-app)

Looking for alternatives? Here are some other Ethereum dev kits:

- [Truffle](https://github.com/trufflesuite/truffle)

Questions? Feedback? [Please let us know](https://github.com/michaelsbradleyjr/create-embark-dapp/issues/new).
