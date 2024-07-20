# PG Token

Basic Token smart contract written in Solidity.

## Description

This is a simple program written in Solidity Programming Language. It's a smart contract that create a simple token with the Name, the abbreviation and the total Supply.

## Program Execution

You can you [Remix](https://remix.ethereum.org) to execute this program. [Remix](https://remix.ethereum.org) is an online Solidity IDE.

Create a file called `token.sol`. Copy and paste the following code.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "PG Token";
    string public tokenAbbr = "PGT";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

Navigate to the `Solidity Compiler` tab at the top left corner of the window and click on `Compile token.sol`. After that, goto the `Deploy & run transaction` tab, then click on `Deploy`. Here we have a token smart contract :).

## Author

**[Adesanmi D. PraiseGod](https://www.linkedin.com/in/praisegod)**
_[dayopraisegod@gmail.com](dayopraisegod@gmail.com)_

## License

This program is licensed under [MIT License](./LICENSE).
