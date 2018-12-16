# solidity-upgrade

This is a work in progress [Prettier Plugin](https://prettier.io/docs/en/plugins.html) for Refactoring [Solidity](https://github.com/ethereum/solidity) 0.4.x code to 0.5.x code.
This tool does the following tasks currently:
1) Change pragma version to `^0.5.0`.
2) Add `calldata` storage keyword infront of `external` function parameters and `memory` infront of other function's parameters that don't already have a defined parameter storage location.

## Installation 

Install both `prettier` and `solidity-refactor`:

```
npm install --save-dev prettier solidity-refactor
```

## Usage

This plugin allows you to [configure prettier](https://prettier.io/docs/en/options.html) to your needs. Command with my personal config is

```
prettier --write --tab-width 4 --print-width 140 '**/*.sol'
```
