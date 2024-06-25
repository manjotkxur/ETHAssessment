#ETHassessment 
Presenting a simple Solidity smart contract that represents a token with necessary functions such as token burning and minting. These function are used to add or subtract the values from thr existing value inside the token.

##Description
This program is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.It demonstrates various concepts taught in the ETH Beginner Course. The contract includes public variables for storing token details, a mapping to associate addresses with balances, a mint function that accepts an address and a value as parameters, and a burn function with similar parameters. These function are used to add or subtract the values from thr existing value inside the token respectively.

##Getting started and Code

###Installing
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

    }
}
```
###Executing Program
Creating the contract named MyToken. This contract will have public variables i.e., the name of the token (in this case: MOVIN) & the abbreviation for that name (in this case: XYZABC). Along with these public string type variables there will be an additional third public variable i.e., an unassigned integer named total_Supply which is always positive. This variable holds the initial value of the token (in this case: zero). 
```javascript

contract MyToken {

    // public variables here
    string public Token_Name ="MOVIN";
    string public Token_Abbrev="XYZABC";
    uint public total_Supply = 0;
```
Hereafter, Mapping is carried out. Mapping in Solidithy is a data structure that can store a pair of interrelated values i.e., the pair of address of the token (address) & the unsigned integer value stored inside the token (uint). Here, Mapping is named as balances.
```javascript

 // mapping variable here
    mapping(address => uint) public balances;
```
Henceforth, Fuction mint is created. The purpose of this function is the add new value into the existing value inside the token. This function accept two parameters i.e., address & uint value (both from the mapping data structure). The uint value is added to the total_Supply which is then updated at the address of the token using the mapping 'balances'.
```javascript

 // mint function
    function mint (address _address, uint _value) public {
        total_Supply += _value;
        balances[_address] +=_value;
    }
```
Furthermore, Function burn is created. The purpose of this function is the subtract new value from the existing value inside the token. This function accept two parameters i.e., address & uint value (both from the mapping data structure). Firstly, it is checked if the existing value inside the token is larger than the value to be burnt. If yes, the uint value is then subtracted from the total_Supply which is then updated at the address of the token using the mapping 'balances'.
```javscript

// burn function
     function burn (address _address, uint _value) public {
      if (balances[_address] >= _value){
        total_Supply -= _value;
        balances[_address] -=_value;
    } //close if
} //close burn fuction
} //close contract
```
##Help
If you encounter any issues, ensure that you have the correct versions of Node.js, Truffle, and Ganache installed. For more detailed help, refer to the official documentation of these tools.
Common problems or issues
Error in compilation: Make sure your Solidity version in truffle-config.js matches the version specified in the contract.
Deployment issues: Ensure that your local blockchain (Ganache) is running before deploying.

###Command to run if program contains helper info
```javascript

truffle help
```
##Author
https://github.com/manjotkxur
Key role: Constructed & documented the project.

##Liscence
This project is licensed under the License of Author. Contact the author for any further details.
