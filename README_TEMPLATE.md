# Simple Contract for Solidity

A simple implementation of a token on the blockchain. It allows users to mint (create) and burn (destroy) tokens.

## Description

This contract provides a basic structure for creating and managing tokens on blockchain with the functions: Mint and Burn. It allows the users to track the gas fees and check whether the balances are working as intended before using on future projects.

## Getting Started

### Executing program

* To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
* Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., test1.sol). Copy and paste the following code into the file:
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
   string public tokenName = "MIASMA"; 
   string public tokenAbbrv = "MSA";
   uint public totalSupply = 0;
   
    // mapping variable here
   mapping(address => uint) public balances;

    // mint function
   function mint (address Taddress , uint Tvalue) public {
      totalSupply += Tvalue;
      balances[Taddress] += Tvalue;
   }
   
    // burn function
   function burn (address Taddress , uint Tvalue) public {
      if (balances[Taddress] >= Tvalue) {
      totalSupply -= Tvalue;
      balances[Taddress] -= Tvalue;
      }
   }
}
```

*To compile the code, Head over to the left side menu bar and click on the "Solidity Compiler".

*Click the Compile (filename.sol).

*Under the "Solidity Compiler" Click on to "Deploy and Run Transactions".

*Click on the Deploy Button.

*Scroll down to the deployed contracts tab by clicking the drop-down arrow.

*In here, you will see the variables we have created on the compiler and adjust it to your preferences for checking out the functions.

*Copy the address on the accounts field and paste it whether on mint or burn address fields together with a specified value.

*Click on the variables to refresh the value.

## Authors

Jayson Banjawan 

[jeysuhnn09](https://www.facebook.com/Jeysuhnn09)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
