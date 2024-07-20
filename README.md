# Project Title

MyToken Smart Contract

## Overview

A simple smart contract for an ERC20-like token named Cipher (Cip). This contract includes functionalities for minting and burning tokens while tracking total supply and individual balances.

## Description

The MyToken smart contract is designed to illustrate the basics of creating and managing a custom token on the Ethereum blockchain. It includes:
- Public variables for the token's name, abbreviation, and total supply.
- A mapping of addresses to balances.
- A `mint` function to create new tokens and assign them to a specified address.
- A `burn` function to destroy tokens from a specified address, ensuring the address has sufficient balance.

This project serves as a foundational example for understanding how to implement and interact with custom tokens using Solidity.

## Getting Started

### Installing

To set up the project, you'll need:
- Solidity compiler (e.g., through Remix, Truffle, or Hardhat)

**Download the project:**
```bash
git clone https://github.com/IshaL-30/Metacrafter_Course.git
cd Assignment2/create_a_token.sol
```

### Executing program

## Deploying the Smart Contract

To deploy and interact with the smart contract:

- Ensure you have a Solidity development environment set up (e.g., Remix, Truffle, Hardhat).
- Copy the smart contract code into a new Solidity file (e.g., MyToken.sol).
- Compile the contract using your development environment.
- Deploy the contract to a local Ethereum network or a testnet.
- Interact with the contract using the provided functions (mint and burn).

Example Commands
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "QWE";
    string public tokenAbbrv = "RTY";
    uint public totalSupply = 0;
    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

## Help

For any issues or questions, please refer to the following resources:

Solidity Documentation
Common issues may include:

Incorrect installation paths
Version mismatches between Solidity compiler and your development environment
Feel free to reach out for further assistance.

## Authors

Contributors names and contact info

[https://www.linkedin.com/in/isha-limbasiya/](https://www.linkedin.com/in/edison-tomas-1568a2319/)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
