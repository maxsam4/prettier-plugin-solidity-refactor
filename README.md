# solidity-upgrade

This is a work in progress [Prettier Plugin](https://prettier.io/docs/en/plugins.html) for Refactoring [Solidity](https://github.com/ethereum/solidity) 0.4.x code to 0.5.x code.
This tool does the following tasks currently:
1) Change pragma version to `^0.5.0`.
2) Add `calldata` storage keyword infront of `external` function complex parameters and `memory` infront of other function's complex parameters that don't already have a defined parameter storage location.
3) Rename constructor function from `function ContractName` to `constructor`.
4) Add default function visibility of `public` to those normal functions which don't have function visibility explicitly defined.
5) Add function visibility of `external` to fallback functions and all functions of inteface.
6) Prettify your code using prettier.


## Installation 

Install both `prettier` and `prettier-plugin-solidity-refactor`:

```
npm install --save-dev prettier prettier-plugin-solidity-refactor
```
OR
```
yarn add --dev prettier prettier-plugin-solidity-refactor
```

## Usage

This plugin allows you to [configure prettier](https://prettier.io/docs/en/options.html) to your needs. Command with my personal config is

```
./node_modules/.bin/prettier --write --tab-width 4 --print-width 140 '**/*.sol'
```

OR command with default config is
```
./node_modules/.bin/prettier --write '**/*.sol'
```

You may add the command script to your package.json file and then use `npm run scriptName` to execute the command.
