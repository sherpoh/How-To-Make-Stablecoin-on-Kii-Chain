# 🪙 How to Create a Stablecoin on Kii Chain Part 1
This project is a practical guide to creating and testing an ERC20-based stablecoin on Kii Chain. The stablecoin created is called IDR, and anyone can mint it simply by entering a wallet address into the mint form—no need for a wallet connection like Metamask.

The goals of this project are:
- Provide a real-world example of creating a stablecoin on Kii Chain
- Demonstrate an open and transparent minting process
- Encourage other builders to experiment and contribute to the Kii ecosystem

## 🧩 Token Creation Steps
### 1. Initial Explanation
We will create an ERC20 token called IDR that functions as a stablecoin. This token can be minted by anyone through a simple web interface. No wallet connection is required—simply enter the destination address and click "Mint".

### 2. Set Up Solidity
Use the standard ERC20 template. Add a publicly callable mint(address to, uint256 amount) function (for demo purposes). Save the TokenIDR.sol file in [Remix](https://remix.ethereum.org/)

**<mark>TokenIDR.sol</mark>**
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract IDRStablecoin is ERC20 { 
constructor() ERC20("Indonesian Rupiah", "IDR") {} 

function decimals() public view virtual override returns (uint8) { 
return 6; 
} 

function mint(address to, uint256 amount) public { 
_mint(to, amount); 
}
}
```
### 3. Deploy
Deploy the contract to the Kii Chain testnet (or another compatible EVM network if not available yet). Save the contract address and ABI for use in the frontend.

### 4. Test Mint in Remix
Open the Remix IDE, paste the Solidity code, deploy it, and test the mint() function by entering the destination address and token amount.

### 5. Deploy to Web (Mint)
Create an HTML/JS page with an input form for the address and token amount. Add a "Mint" button that calls the mint() function directly to the contract using ethers.js. No wallet connection is required.

### 6. Done
The IDR stablecoin is ready to be used and minted by anyone. This repository can be used as a template for other stablecoins in the Kii Chain ecosystem.
