# solidity
Step 1: Set up the Development Environment
To get started, you need to set up your development environment. Here's what you'll need:

Install Node.js: Solidity development often involves using Node.js and npm (Node Package Manager). You can download Node.js from the official website (https://nodejs.org) and follow the installation instructions.

Install Solidity Compiler: You'll need the Solidity compiler to compile your smart contracts. The most popular compiler is solc. You can install it globally using npm by running the 

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
    string public tokenName="Ashish";
    string public takearr ="Ah";
    uint public totalSupply = 0;
    //mapping variable here
    mapping(address => uint) public balanceof;
    //mint function
   function mint(address _address, uint _value) public{
        totalSupply += _value;
        balanceof[_address] += _value; 
   }
         //burn function
    function burn (address _address, uint _value) public{
        totalSupply -= _value;
        balanceof[_address] -= _value;
    }
}
 
