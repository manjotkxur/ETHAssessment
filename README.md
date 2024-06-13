#ETHassessment 
Presenting a simple Solidity smart contract that represents a token with necessary functions such as token burning and minting.

##Description
This program is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.It demonstrates various concepts taught in the ETH Beginner Course. The contract includes public variables for storing token details, a mapping to associate addresses with balances, a mint function that accepts an address and a value as parameters, and a burn function.

##Getting started and Code
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., eth.sol). Copy and paste the following code into the file:
```javascript

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

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
    string public Token_Name ="MOVIN";
    string public Token_Abbrev="XYZABC";
    uint public total_Supply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        total_Supply += _value;
        balances[_address] +=_value;
    }

    // burn function
     function burn (address _address, uint _value) public {
      if (balances[_address] >= _value){
        total_Supply -= _value;
        balances[_address] -=_value;
    }
```
    }


}

##Overview
This project aims to provide users with a hands-on grasp of the several ideas covered in the ETH Beginner Course on Solidity.
