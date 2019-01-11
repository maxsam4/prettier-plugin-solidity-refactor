# Solidity Refactor

This is a work in progress [Prettier Plugin](https://prettier.io/docs/en/plugins.html) for Refactoring [Solidity](https://github.com/ethereum/solidity) 0.4.X code to 0.5.X code.
This tool does the following tasks currently to refactor your soldiity 0.4.X code to work with solidity 0.5.X:
1) Change pragma version to `^0.5.0`.
2) Add `calldata` storage keyword infront of `external` function complex parameters and `memory` infront of other function's complex parameters that don't already have a defined parameter storage location.
3) Rename constructor function from `function ContractName` to `constructor`.
4) Add default function visibility of `public` to those normal functions which don't have function visibility explicitly defined.
5) Add function visibility of `external` to fallback functions and all functions of any interface.
6) Convert `constant` function state mutability modifier to `view`.
7) Prettify your code using prettier.


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
OR command with default config that will just print changed contracts to stdout instead of actually making chnages:
```
./node_modules/.bin/prettier '**/*.sol'
```

You may add the command script to your package.json file and then use `npm run scriptName` to execute the command.

### Known limitations
1) It does not add `payable` to addresses as it can not detect which addresses require to be payable. If you are using `addressA.send` or `addressA.transfer`, please manually declare them as `address payable addressA` rather than `address addressA`.
2) It does not redefine expired variables. In solidity 0.4.X, variables persisted even outside their scope but in soldiity 0.5.x, you need to define them again.
3) It does not fix illegal implicit conversions.
4) Low level `call` now returns 2 parameters rather than 1. This plugin does not rafactor it.

### Known bugs
None. Please report the bugs you may find.

### TODO
1) Add test cases.

### Contributions of any kind are welcome.
NOTE: This tool is still under early testing. Please always manually verify all your contracts after using this tool.
