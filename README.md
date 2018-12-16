# solidity-upgrade

This is a work in progress [Prettier Plugin](https://prettier.io/docs/en/plugins.html) for Refactoring [Solidity](https://github.com/ethereum/solidity) 0.4.x code to 0.5.x code.

## Installation and usage

Install both `prettier` and `prettier-plugin-solidity`:

```
npm install --save-dev prettier prettier-plugin-solidity
```

You can add a script for running prettier on all your contracts:

```
"prettier": "prettier --write **/*.sol"
```

Or you can use it as part of your linting to check that all your code is prettified:

```
"lint": "prettier --list-different **/*.sol"
```
