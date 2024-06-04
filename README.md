# MyToken Smart Contract

## Overview
This Solidity smart contract implements a basic token system with minting and burning functionalities. The token has a name, abbreviation, and total supply, and supports balance management for different addresses.

## Contract Details

### Public Variables
- `tokenName`: Name of the token (e.g., "CATIE").
- `tokenAbbrv`: Abbreviation of the token (e.g., "CTE").
- `totalSupply`: Total supply of the token in circulation.

### Mapping
- `balances`: Mapping of addresses to their respective token balances.

### Functions

#### `mint(address _address, uint _value)`
- Increases the total supply by `_value`.
- Adds `_value` tokens to the balance of `_address`.

#### `burn(address _address, uint _value)`
- Decreases the total supply by `_value`.
- Deducts `_value` tokens from the balance of `_address`.
- Requires that `_address` has a balance greater than or equal to `_value`.

## Usage

### Mint Tokens
```solidity
mint(address _address, uint _value)
```
- Example: `mint(0x123..., 100);` increases the total supply and the balance of `0x123...` by 100 tokens.

### Burn Tokens
```solidity
burn(address _address, uint _value)
```
- Example: `burn(0x123..., 50);` decreases the total supply and the balance of `0x123...` by 50 tokens.
- Reverts if `0x123...` has less than 50 tokens.

## Error Handling
- The `burn` function uses `require` to ensure the sender's balance is sufficient before burning tokens.

