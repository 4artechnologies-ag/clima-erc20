## ERC-20 Token

This is an ERC-20 token in solidity language of an ERC-20 standard Ethereum , mintable and burnable, with minter,admin, access permissions and pausable module.

- [Contract Address](https://etherscan.io/address/0x1409d601f0a3f8cfc615d7d5ce4454c6ca5f8b77#code)
- Name: ClimaCoin
- Symbol: CC
- Total Cap: 2,208,740,668


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

The view function `balanceOf` returns the account balance of an account.
 
#### Allowance

The view function `allowance` returns the amount which address `spender` is allowed to spend from another account - `owner`.

#### Transfer and Transfer From

The method `transfer` is called by `msg.sender` account and transfers `amount` amount of tokens to another address `to`.

The method `transferFrom` allows one third account `msg.sender` transfers `amount` amount of tokens from other address `from` to other address `to`. The `from` address needs to approve `msg.sender` spend the `amount` first.

Both methods fire the `Transfer` event.

#### Approve

The method `approve` allows one account - `spender` - to spend from another account - `msg.sender` - the `amount`.
 
#### Increase Approval and Decrease Approval
 

The method `increaseApproval` allows another account - `spender` - to spend from another account - `msg.sender` - adding to current allowance the `addedValue` amount.

The method `decreaseApproval` reduces the value approved to `spender` to spend from another account - `msg.sender` - subtracting the `subtractedValue` from the current approval amount. If the `subtractedValue` is bigger than current approval the value will reduce to 0.

#### Mint, Burn and Burn From

The `mint` function creates `amount` tokens and assigns them to account `to`, increasing the total supply. Only the user with minter role can mint.

The `burn` function destroys `amount` tokens from `msg.sender`, reducing the total supply.

The `burnFrom` function destroys `amount` tokens from account `from`, reducing the total supply. The `from` address needs to approve the `msg.sender` address spend the `amount` first.

All these methods fire the `Transfer` event.

## Erc-20 Modules


#### Pausable

Contract module which allows children to implement an emergency stop mechanism that can be triggered by an authorized account.
only the pauser account can trigger call `pause` and `unpause` methods.

### Access Control Roles
contract module which will assign access roles to different users by authorized account.
olny the admin accont can trigger call `grantRole`, `getRoleAdmin`, `revokeRole`, amd `hasRole` methods.

### Cap 
contract module which will allow the authorized account to set the total supply of the token.
anyone account can trigger call `cap` methods to get the value in cap.