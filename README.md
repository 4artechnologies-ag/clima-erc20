## ERC-20 Token

This is an ERC-20 token in solidity language of an ERC-20 standard Ethereum , mintable and burnable, with minter,admin, access permissions and pausable module.

## Erc-20 implementation

ERC-20 is a standard interface for tokens.

More Information about Solidity Language and ERC-20 Standard:

- [Solidity](https://solidity.readthedocs.io/en/v0.8.16/): `v0.8.16`
- [ERC-20](https://eips.ethereum.org/EIPS/eip-20)

This repository contains an ERC-20 implementetion that can be found at root.

### Erc-20 Methods

#### Constructor

The `constructor` function sets `name`, `symbol`, `decimals` and `totalCap` of the token.

#### Balance

The view function `balanceOf` returns the account balance of an account `_owner`.
 
#### Allowance

The view function `allowance` returns the amount which address `_spender` is allowed to spend from another account - `_owner`.

#### Transfer and Transfer From

The method `transfer` is called by `msg.sender` account and transfers `_value` amount of tokens to another address `_to`.

The method `transferFrom` allows one third account `msg.sender` transfers `_value` amount of tokens from other address `_from` to other address `_to`. The `_from` address needs to approve `msg.sender` spend the `_value` first.

Both methods fire the `Transfer` event.

#### Approve

The method `approve` allows one account - `_spender` - to spend from another account - `msg.sender` - the `_amount`.
 
#### Increase Approval and Decrease Approval
 
Those methods are not a ERC-20 standard but can be used to manage the value of the allowances.

The method `increaseApproval` allows another account - `_spender` - to spend from another account - `msg.sender` - adding to current allowance the `_addedValue` amount.

The method `decreaseApproval` reduces the value approved to `_spender` to spend from another account - `msg.sender` - subtracting the `_subtractedValue` from the current approval amount. If the `_subtractedValue` is bigger than current approval the value will reduce to 0.

#### Mint, Burn and Burn From

Those methods are not a ERC-20 standard but are commonly used to create and destroy tokens.

The `mint` function creates `amount` tokens and assigns them to account `to`, increasing the total supply. Only the smart contract owner can mint.

The `burn` function destroys `amount` tokens from `msg.sender`, reducing the total supply.

The `burnFrom` function destroys `amount` tokens from account `from`, reducing the total supply. The `from` address needs to approve the `msg.sender` address spend the `amount` first.

All these methods fire the `Transfer` event.

## Erc-20 Modules in this example


#### Pausable

Contract module which allows children to implement an emergency stop mechanism that can be triggered by an authorized account.

In this example, only the pauser account can trigger call `pause` and `unpause` methods.

