# Assessment Smart Contract

## Overview

The `Assessment` smart contract is a Solidity-based Ethereum contract designed for basic financial operations, including depositing, withdrawing, and transferring funds. The contract is owner-controlled, allowing only the owner to execute these operations. Additionally, it provides utility functions to check the remaining gas and retrieve the current blockchain ID.

## Features

- **Owner Control**: Only the owner of the contract can perform deposits, withdrawals, and transfers.
- **Deposit Funds**: Owners can deposit funds into the contract.
- **Withdraw Funds**: Owners can withdraw a specified amount of funds from the contract.
- **Transfer Funds**: Owners can transfer funds to a specified recipient address.
- **Balance Check**: Retrieve the current balance of the contract.
- **Gas Remaining**: Check the remaining gas available for transactions.
- **Chain ID**: Retrieve the current blockchain ID.

## Events

The contract emits the following events:

- `Deposit(uint256 amount)`: Emitted when funds are deposited.
- `Withdraw(uint256 amount)`: Emitted when funds are withdrawn.
- `Transfer(address indexed recipient, uint256 amount)`: Emitted when funds are transferred to a recipient.
- `ContractDestroyed(address indexed recipient, uint256 amount)`: Emitted when the contract is destroyed (though this functionality is not currently implemented).

## Error Handling

The contract defines a custom error `InsufficientBalance(uint256 balance, uint256 withdrawAmount)` for handling withdrawal attempts that exceed the current balance.

## Functions

### Constructor

```solidity
constructor(uint256 initBalance) payable
Initializes the contract with a specified initial balance.
getBalance()
solidity
Copy code
function getBalance() public view returns(uint256)
Returns the current balance of the contract.
deposit(uint256 _amount)
solidity
Copy code
function deposit(uint256 _amount) public payable
Allows the owner to deposit funds into the contract.
withdraw(uint256 _withdrawAmount)
solidity
Copy code
function withdraw(uint256 _withdrawAmount) public
Allows the owner to withdraw a specified amount of funds. Emits InsufficientBalance error if the balance is insufficient.
transfer(address payable recipient, uint256 _amount)
solidity
Copy code
function transfer(address payable recipient, uint256 _amount) public
Allows the owner to transfer a specified amount of funds to a recipient.
getgasRemaining()
solidity
Copy code
function getgasRemaining() public view returns(uint)
Returns the remaining gas for the current transaction.
getchainIdCurrent()
solidity
Copy code
function getchainIdCurrent() public view returns(uint)
Returns the current blockchain ID.
Deployment
To deploy the contract, use the following command in your preferred Ethereum development environment:

bash
Copy code
npx hardhat run scripts/deploy.js
Replace scripts/deploy.js with the path to your deployment script.

License
