# ERC-20 Kitty Token Contract

This Solidity program is a demonstration of ERC-20 Token with support of transfer, minting, and burning of coins.

## Description

This Solidity program defines an ERC20 token with essential functionalities. It includes functions for minting, where only the founder of the token can create new tokens, and burning, which allows any holder to destroy their tokens. Additionally, the contract supports standard ERC20 transfer and allowance operations, enabling tokens to be transferred between any accounts on the blockchain. It imports the IERC20 interface from [OpenZeppelin](https://www.openzeppelin.com/)

# Contract Overview
The Token contract is a basic implementation of an ERC20-like token. It features the following components:

1) `name`: The name of the token. <br>

2) `symbol`: The symbol of the token. <br>

3) `founder`: The address that deploys the contract and holds the initial supply of tokens. <br>

4) `balances`: A mapping of addresses to their token balances. <br>

5) `tokenTotalSupply`: The total supply of tokens in the contract. <br>

6) `allowances`: A mapping of allowances between addresses.

# Usage
Constructor
The contract constructor initializes the contract with an initial supply of tokens. The deploying address becomes the founder of the contract and holds the entire initial supply.

```solidity
constructor(string memory _name, string memory _symbol, uint _tokenTotalSupply);
```

# Functions
```solidity
totalSupply();
// Returns the total supply of tokens in the contract.
```

```solidity
balanceOf(address account);
// Returns the token balance of a given address.
```

```solidity
transfer(address recipient, uint256 amount);
// Allows users to transfer tokens to another address. Caller's balance is reduced, and recipient's balance is increased.
```

```solidity
allowance(address owner, address spender);
// Returns the remaining number of tokens that `spender` is allowed to spend on behalf of `owner`.
```

```solidity
approve(address spender, uint256 amount);
// Sets the allowance for `spender` over the caller's tokens.
```

```solidity
transferFrom(address sender, address recipient, uint256 amount);
// Transfers `amount` of tokens from `sender` to `recipient`, using the allowance mechanism.
```

```solidity
mint(address recipient, uint256 amount);
// Allows the founder to mint new tokens and add them to a specified address's balance.
```

```solidity
burn(uint256 amount);
// Allows users to burn (destroy) a specific amount of their tokens. The caller's balance and the total supply are reduced accordingly.
```

## Getting Started

### Installation
[Open this program in Remix](https://remix.ethereum.org/#code=Ly8gU1BEWC1MaWNlbnNlLUlkZW50aWZpZXI6IE1JVApwcmFnbWEgc29saWRpdHkgXjAuOC4yNjsKCmltcG9ydCB7SUVSQzIwfSBmcm9tICJAb3BlbnplcHBlbGluL2NvbnRyYWN0cy90b2tlbi9FUkMyMC9JRVJDMjAuc29sIjsKCmNvbnRyYWN0IG15VG9rZW4gaXMgSUVSQzIwIHsKICAgIHN0cmluZyBwdWJsaWMgbmFtZTsKICAgIHN0cmluZyBwdWJsaWMgc3ltYm9sOwogICAgYWRkcmVzcyBwdWJsaWMgZm91bmRlcjsKICAgIHVpbnQyNTYgcHVibGljIHRva2VuVG90YWxTdXBwbHk7CiAgICBtYXBwaW5nKGFkZHJlc3M9PnVpbnQyNTYpIGJhbGFuY2VzOwogICAgbWFwcGluZyhhZGRyZXNzID0+IG1hcHBpbmcoYWRkcmVzcyA9PiB1aW50MjU2KSkgYWxsb3dhbmNlczsKCiAgICBjb25zdHJ1Y3RvcihzdHJpbmcgbWVtb3J5IF9uYW1lLCBzdHJpbmcgbWVtb3J5IF9zeW1ib2wsIHVpbnQgX3Rva2VuVG90YWxTdXBwbHkpIHsKICAgICAgICBuYW1lID0gX25hbWU7CiAgICAgICAgc3ltYm9sID0gX3N5bWJvbDsKICAgICAgICBmb3VuZGVyID0gbXNnLnNlbmRlcjsKICAgICAgICB0b2tlblRvdGFsU3VwcGx5ID0gX3Rva2VuVG90YWxTdXBwbHk7CiAgICAgICAgYmFsYW5jZXNbZm91bmRlcl09IHRva2VuVG90YWxTdXBwbHk7CiAgICB9CgogICAgZnVuY3Rpb24gdG90YWxTdXBwbHkoKSBwdWJsaWMgdmlldyBvdmVycmlkZSByZXR1cm5zICh1aW50MjU2KSB7CiAgICAgICAgcmV0dXJuIHRva2VuVG90YWxTdXBwbHk7CiAgICB9CgogICAgZnVuY3Rpb24gYmFsYW5jZU9mKGFkZHJlc3MgYWNjb3VudCkgcHVibGljIHZpZXcgb3ZlcnJpZGUgcmV0dXJucyAodWludDI1NikgewogICAgICAgIHJldHVybiBiYWxhbmNlc1thY2NvdW50XTsKICAgIH0KCiAgICBmdW5jdGlvbiB0cmFuc2ZlcihhZGRyZXNzIHJlY2lwaWVudCwgdWludDI1NiBhbW91bnQpIHB1YmxpYyBvdmVycmlkZSByZXR1cm5zIChib29sKSB7CiAgICAgICAgcmVxdWlyZShhbW91bnQ+MCwgIkludmFsaWQgdHJhbnNmZXIgYW1vdW50Iik7CiAgICAgICAgcmVxdWlyZShiYWxhbmNlc1ttc2cuc2VuZGVyXSA+PSBhbW91bnQsICJJbnN1ZmZpY2llbnQgYmFsYW5jZSIpOwoKICAgICAgICBiYWxhbmNlc1ttc2cuc2VuZGVyXSAtPSBhbW91bnQ7CiAgICAgICAgYmFsYW5jZXNbcmVjaXBpZW50XSArPSBhbW91bnQ7CgogICAgICAgIGVtaXQgVHJhbnNmZXIobXNnLnNlbmRlciwgcmVjaXBpZW50LCBhbW91bnQpOwogICAgICAgIHJldHVybiB0cnVlOwogICAgfQoKICAgIGZ1bmN0aW9uIGFsbG93YW5jZShhZGRyZXNzIG93bmVyLCBhZGRyZXNzIHNwZW5kZXIpIHB1YmxpYyB2aWV3IG92ZXJyaWRlIHJldHVybnMgKHVpbnQyNTYpIHsKICAgICAgICByZXR1cm4gYWxsb3dhbmNlc1tvd25lcl1bc3BlbmRlcl07CiAgICB9CgogICAgZnVuY3Rpb24gYXBwcm92ZShhZGRyZXNzIHNwZW5kZXIsIHVpbnQyNTYgYW1vdW50KSBwdWJsaWMgb3ZlcnJpZGUgcmV0dXJucyAoYm9vbCkgewogICAgICAgIHJlcXVpcmUoYW1vdW50PjAsICJJbnZhbGlkIGFsbG93YW5jZSBhbW91bnQiKTsKCiAgICAgICAgYWxsb3dhbmNlc1ttc2cuc2VuZGVyXVtzcGVuZGVyXSA9IGFtb3VudDsKICAgICAgICAKICAgICAgICBlbWl0IEFwcHJvdmFsKG1zZy5zZW5kZXIsIHNwZW5kZXIsIGFtb3VudCk7CiAgICAgICAgcmV0dXJuIHRydWU7CiAgICB9CgogICAgZnVuY3Rpb24gdHJhbnNmZXJGcm9tKGFkZHJlc3Mgc2VuZGVyLCBhZGRyZXNzIHJlY2lwaWVudCwgdWludDI1NiBhbW91bnQpIHB1YmxpYyBvdmVycmlkZSByZXR1cm5zIChib29sKSB7CiAgICAgICAgcmVxdWlyZShhbW91bnQ+MCwgIkludmFsaWQgYWxsb3dhbmNlIGFtb3VudCIpOwogICAgICAgIHJlcXVpcmUoYmFsYW5jZXNbc2VuZGVyXSA+PSBhbW91bnQsICJJbnN1ZmZpY2llbnQgc3VwcGx5Iik7CiAgICAgICAgcmVxdWlyZShhbW91bnQ8PWFsbG93YW5jZXNbc2VuZGVyXVtyZWNpcGllbnRdLCAiVGhpcyBhbW91bnQgaXMgbm90IGFsbG93ZWQiKTsKCiAgICAgICAgYWxsb3dhbmNlc1tzZW5kZXJdW3JlY2lwaWVudF0gLT0gYW1vdW50OwogICAgICAgIGJhbGFuY2VzW3NlbmRlcl0gLT0gYW1vdW50OwogICAgICAgIGJhbGFuY2VzW3JlY2lwaWVudF0gKz1hbW91bnQ7CgogICAgICAgIGVtaXQgVHJhbnNmZXIoc2VuZGVyLCByZWNpcGllbnQsIGFtb3VudCk7CiAgICAgICAgcmV0dXJuIHRydWU7CiAgICB9CgogICAgZnVuY3Rpb24gbWludChhZGRyZXNzIHJlY2lwaWVudCwgdWludDI1NiBhbW91bnQpIHB1YmxpYyByZXR1cm5zKGJvb2wpIHsKICAgICAgICByZXF1aXJlKG1zZy5zZW5kZXIgPT0gZm91bmRlciwgIlVuYXV0aG9yaXplZCIpOwoKICAgICAgICBiYWxhbmNlc1tyZWNpcGllbnRdICs9IGFtb3VudDsKICAgICAgICB0b2tlblRvdGFsU3VwcGx5ICs9IGFtb3VudDsKCiAgICAgICAgZW1pdCBUcmFuc2ZlcihhZGRyZXNzKDApLCByZWNpcGllbnQsIGFtb3VudCk7CiAgICAgICAgcmV0dXJuIHRydWU7CiAgICB9CgogICAgZnVuY3Rpb24gYnVybih1aW50MjU2IGFtb3VudCkgcHVibGljIHJldHVybnMoYm9vbCkgewogICAgICAgIHJlcXVpcmUoYmFsYW5jZXNbbXNnLnNlbmRlcl0+PWFtb3VudCwgIkluc3VmZmljaWVudCBiYWxhbmNlIik7CgogICAgICAgIGJhbGFuY2VzW21zZy5zZW5kZXJdIC09IGFtb3VudDsKICAgICAgICB0b2tlblRvdGFsU3VwcGx5IC09IGFtb3VudDsKCiAgICAgICAgZW1pdCBUcmFuc2Zlcihtc2cuc2VuZGVyLCBhZGRyZXNzKDApLCBhbW91bnQpOwogICAgICAgIHJldHVybiB0cnVlOwogICAgfQoKfQ&lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.26+commit.8a97fa7a.js)

### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).


```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";

contract myToken is IERC20 {
    string public name;
    string public symbol;
    address public founder;
    uint256 public tokenTotalSupply;
    mapping(address=>uint256) balances;
    mapping(address => mapping(address => uint256)) allowances;

    constructor(string memory _name, string memory _symbol, uint _tokenTotalSupply) {
        name = _name;
        symbol = _symbol;
        founder = msg.sender;
        tokenTotalSupply = _tokenTotalSupply;
        balances[founder]= tokenTotalSupply;
    }

    function totalSupply() public view override returns (uint256) {
        return tokenTotalSupply;
    }

    function balanceOf(address account) public view override returns (uint256) {
        return balances[account];
    }

    function transfer(address recipient, uint256 amount) public override returns (bool) {
        require(amount>0, "Invalid transfer amount");
        require(balances[msg.sender] >= amount, "Insufficient balance");

        balances[msg.sender] -= amount;
        balances[recipient] += amount;

        emit Transfer(msg.sender, recipient, amount);
        return true;
    }

    function allowance(address owner, address spender) public view override returns (uint256) {
        return allowances[owner][spender];
    }

    function approve(address spender, uint256 amount) public override returns (bool) {
        require(amount>0, "Invalid allowance amount");

        allowances[msg.sender][spender] = amount;
        
        emit Approval(msg.sender, spender, amount);
        return true;
    }

    function transferFrom(address sender, address recipient, uint256 amount) public override returns (bool) {
        require(amount>0, "Invalid allowance amount");
        require(balances[sender] >= amount, "Insufficient supply");
        require(amount<=allowances[sender][recipient], "This amount is not allowed");

        allowances[sender][recipient] -= amount;
        balances[sender] -= amount;
        balances[recipient] +=amount;

        emit Transfer(sender, recipient, amount);
        return true;
    }

    function mint(address recipient, uint256 amount) public returns(bool) {
        require(msg.sender == founder, "Unauthorized");

        balances[recipient] += amount;
        tokenTotalSupply += amount;

        emit Transfer(address(0), recipient, amount);
        return true;
    }

    function burn(uint256 amount) public returns(bool) {
        require(balances[msg.sender]>=amount, "Insufficient balance");

        balances[msg.sender] -= amount;
        tokenTotalSupply -= amount;

        emit Transfer(msg.sender, address(0), amount);
        return true;
    }

}
```

## Help
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Token" contract from the dropdown menu, and then click on the "Deploy" button.

## Authors
Ankush Kumar

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
