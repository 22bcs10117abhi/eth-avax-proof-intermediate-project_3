# Introduction

The provided code is a Solidity smart contract that implements a basic ERC20 token called "MyToken". The contract inherits from the ERC20 and Ownable contracts from the OpenZeppelin library, which provide standard ERC20 functionality and access control, respectively.


# Description

  The provided Solidity code defines a smart contract called MyToken that implements the ERC20 token standard. The contract inherits from the ERC20 and Ownable contracts from the OpenZeppelin library, which provide standard ERC20 functionality and access control, respectively.


# Imports

The contract imports two OpenZeppelin contracts:

    ERC20: Provides the standard ERC20 token functionality, such as token transfer, approval, and total supply management.
    Ownable: Provides access control functionality, allowing a specific address (the owner) to perform privileged actions.


# Getting Started

# Executing program

/ SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyToken is ERC20 {
    constructor() ERC20("MyToken", "MTK") {
        // No need to call the Ownable constructor, it's handled by OpenZeppelin
    }

    function mint(address to, uint256 amount) public {
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(_msgSender(), amount);
    }

    function transfer(address to, uint256 amount) public override returns (bool) {
        _transfer(_msgSender(), to, amount);
        return true;
    }
}





## Authors

Abhishek Kumar  
[@Abhishek](https://www.linkedin.com/in/abhishek-kumar-75273024b/)


## License

This MyToken is licensed under the MIT License 
