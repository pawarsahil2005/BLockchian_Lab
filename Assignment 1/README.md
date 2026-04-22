# Assignment 1: Smart Contract Development

## 📌 Purpose

This assignment demonstrates a minimal smart contract (SimpleStorage) that stores and retrieves a single unsigned integer on-chain. The repository contains the contract source and screenshots showing compile and deploy results.

## Contract (example)

Save the following Solidity contract as `contracts/SimpleStorage.sol` or as `contact.sol` in this folder:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleStorage {
		uint256 private value;

		function set(uint256 _value) public {
				value = _value;
		}

		function get() public view returns (uint256) {
				return value;
		}
}
```

## ⚙️ Functions (details)

- `set(uint256 _value)`: public function, stores `_value` in contract storage.
- `get()`: public view function, returns the stored `uint256` value.

## Project structure (recommended)

- `contracts/` — Solidity contracts (e.g., `SimpleStorage.sol`)
- `scripts/` — deployment scripts (e.g., `deploy.js`)
- `images/` — screenshots (already included)
- `hardhat.config.js` — Hardhat configuration

## Prerequisites

- Node.js (v16+ recommended)
- npm or yarn
- Hardhat (installed per instructions below)

## Setup

Open a terminal in `Assignment 1` and run:

```bash
npm init -y
npm install --save-dev hardhat @nomiclabs/hardhat-ethers ethers
npx hardhat
```

When prompted by `npx hardhat`, choose "Create a basic sample project" (or set up your preferred config). This creates `contracts/`, `scripts/`, and a sample `hardhat.config.js`.

Place the contract above in `contracts/SimpleStorage.sol` (or replace `contact.sol`).

## Compile

Compile the contracts with:

```bash
npx hardhat compile
```

You should see compilation success messages in the terminal (a screenshot is included below).

## Deploy locally

Create a deployment script at `scripts/deploy.js` with the following content:

```javascript
const hre = require("hardhat");

async function main() {
	const SimpleStorage = await hre.ethers.getContractFactory("SimpleStorage");
	const ss = await SimpleStorage.deploy();
	await ss.deployed();
	console.log("SimpleStorage deployed to:", ss.address);
}

main().catch((error) => {
	console.error(error);
	process.exitCode = 1;
});
```

Run a local Hardhat node and deploy to it:

```bash
npx hardhat node
# In a new terminal (still in Assignment 1):
npx hardhat run scripts/deploy.js --network localhost
```

The deploy script prints the contract address on success (a deployment screenshot is included below).

## Interact (optional)

You can use the Hardhat console to interact with the deployed contract:

```bash
npx hardhat console --network localhost
> const SimpleStorage = await ethers.getContractAt("SimpleStorage", "<deployed_address>")
> await SimpleStorage.get()
> await SimpleStorage.set(42)
> await SimpleStorage.get()
```

## 📸 Screenshots

### Compilation success
![Compilation success](images/Screenshot%202026-04-20%20121655.png)

### Deployment success
![Deployment success](images/Screenshot%202026-04-20%20122248.png)

### Additional screenshot
![Additional screenshot](images/Screenshot%202026-04-20%20122653.png)
