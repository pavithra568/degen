# HandbagToken Smart Contract

## Overview

The `HandbagToken` smart contract is an ERC20 token with additional functionalities for minting, burning, and redeeming tokens for different types of handbags. The contract allows the owner to mint tokens and users to transfer, burn, and redeem tokens for handbags.

## Features

- **ERC20 Token**: Implements standard ERC20 functionality.
- **Minting**: Owner can mint new tokens.
- **Burning**: Users can burn their tokens.
- **Handbag Redemption**: Users can redeem tokens for different types of handbags.
- **Balance Checking**: Users can check their token balance.

## Smart Contract Details

### Inheritance

- **`ERC20`**: Implements standard ERC20 functions.
- **`Ownable`**: Provides ownership control.
- **`ERC20Burnable`**: Allows tokens to be burned.

### Events

- **`LogMessage(string message)`**: Emitted for logging messages.

### Enumerations

- **`HandbagType`**: Enum with values `Puma` and `SafariBag`.

### State Variables

- **`handbagPrices`**: Mapping of `HandbagType` to their prices in tokens.
- **`lastPurchasedHandbag`**: Stores the last purchased handbag type.

### Constructor

- **`constructor(address initialOwner)`**: Initializes the contract with the given owner and sets prices for handbags.

### Functions

- **`mintTokens(address to, uint256 amount)`**: Mints new tokens to the specified address. Only callable by the owner.
- **`transferTokens(address to, uint256 amount)`**: Transfers tokens from the caller to the specified address.
- **`redeemHandbag(uint256 tokenAmount)`**: Redeems tokens for a handbag. Burns the required amount of tokens.
- **`getBalance()`**: Returns the token balance of the caller.
- **`burnTokens(uint256 amount)`**: Burns the specified amount of tokens from the caller's balance.
- **`determineHandbagType(uint256 tokenAmount)`**: Internal function to determine the handbag type based on the token amount.
- **`getLastPurchasedHandbag()`**: Returns the last purchased handbag type.
