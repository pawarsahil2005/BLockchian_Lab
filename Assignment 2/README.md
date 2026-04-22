# Assignment 2: Polygon Amoy Deployment

## Objective

The purpose of this assignment is to deploy a simple smart contract to a public blockchain testnet so students can learn the full deployment workflow: preparing Solidity code, compiling, configuring a wallet and network, deploying a contract, and verifying transactions on a block explorer. Deploying to a testnet provides a realistic environment without real monetary risk.

## Network Details

- **Network Name:** Polygon Amoy Testnet
- **RPC URL:** https://rpc.amoy.polygonscan.com
- **Chain ID:** 80002
- **Currency Symbol:** MATIC
- **Block Explorer:** https://amoy.polygonscan.com

> Note: If the RPC URL above becomes unavailable, obtain a working Amoy RPC from official Polygon documentation or a public RPC provider.

## Tools Used

- Remix IDE (https://remix.ethereum.org)
- MetaMask wallet (browser extension)
- Solidity (contract language)

## Smart Contract Code

Create a Solidity file (for example `SimpleStorage.sol`) in Remix and paste the following code. This contract provides `set()` and `get()` functions to store and retrieve a single `uint256` value.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleStorage {
    uint256 private value;

    event ValueChanged(uint256 newValue, address indexed changedBy);

    function set(uint256 _value) public {
        value = _value;
        emit ValueChanged(_value, msg.sender);
    }

    function get() public view returns (uint256) {
        return value;
    }
}
```

## Step-by-step Deployment (Remix + MetaMask)

1. Open Remix IDE
   - Visit `https://remix.ethereum.org` in a Chromium-based browser.

2. Create the contract file
   - In the File Explorer panel create a new file named `SimpleStorage.sol` inside a new folder for this assignment.
   - Paste the `SimpleStorage` contract code above.

3. Compile the contract
   - Open the `Solidity Compiler` tab (left sidebar).
   - Select a compiler version compatible with the contract (e.g., `0.8.x`).
   - Click **Compile SimpleStorage.sol**.
   - Confirm compilation success (look for the green check and no errors).

4. Add Polygon Amoy Testnet to MetaMask
   - Open MetaMask → Settings → Networks → Add Network.
   - Fill in the network details:
     - **Network Name:** Polygon Amoy Testnet
     - **RPC URL:** `https://rpc.amoy.polygonscan.com`
     - **Chain ID:** `80002`
     - **Currency Symbol:** `MATIC`
     - **Block Explorer URL:** `https://amoy.polygonscan.com`
   - Save the network and switch to it.

5. Obtain test MATIC
   - Use an official Amoy faucet if available, or follow instructor guidance to get test tokens. Test MATIC is required to pay gas for deployment and transactions.

6. Connect MetaMask to Remix
   - In Remix, open the `Deploy & Run Transactions` panel.
   - For the **Environment** select `Injected Web3` (this will connect Remix to MetaMask).
   - MetaMask should prompt you to connect; confirm and select an account with test MATIC.

7. Deploy the contract
   - In the `Deploy & Run Transactions` panel, confirm `SimpleStorage` is selected in the contract dropdown.
   - Click **Deploy**.
   - MetaMask will open a transaction confirmation window showing gas estimate and network (Polygon Amoy). Confirm the transaction.
   - Wait for the transaction to be mined; Remix will show the deployed contract instance under `Deployed Contracts`.

8. Copy contract address
   - After deployment, copy the deployed contract address from the Remix `Deployed Contracts` panel.
   - Paste the address in the **0xA97dF270A4F305CB22ba5905847488ce9b727ADD** section below.

9. Verify the transaction on Polygonscan (Amoy)
   - Open `https://amoy.polygonscan.com` and paste the transaction hash or contract address in the search bar.
   - Confirm the transaction status, block number, gas used, and related details.

## Contract Address

Deployed contract address (placeholder):

0xA97dF270A4F305CB22ba5905847488ce9b727ADD

``

Replace the placeholder above with your actual deployed contract address.

## Screenshots

Upload screenshots to the `images` folder. Use the following markdown placeholders (update filenames to match your uploads):

- Compilation success:

  ![Compilation success](images/compilation-success.png)

- Deployment success (Remix & MetaMask confirmation):

  ![Deployment success](images/deployment-success.png)

- Transaction on explorer (Polygonscan Amoy):

  ![Transaction on explorer](images/transaction-explorer.png)

Place your screenshots in `Assignment 2/images/` and ensure filenames match these placeholders.

## Folder Structure

Recommended structure for submission:

```
Assignment 2/
  SimpleStorage.sol
  README.md
  images/
    compilation-success.png
    deployment-success.png
    transaction-explorer.png
```

## Notes

- You will need test MATIC on the Polygon Amoy Testnet to deploy and interact with the contract.
- Never share your MetaMask seed phrase or private key. Keep private keys secure and use test accounts for assignments.
- This assignment uses Remix + MetaMask explicitly — do NOT use Hardhat or Truffle.

## Conclusion

In this assignment you wrote a simple `SimpleStorage` smart contract in Solidity, compiled it with Remix, configured MetaMask for the Polygon Amoy Testnet, deployed the contract, and verified the deployment transaction on the Amoy Polygonscan explorer. This workflow demonstrates the end-to-end process for deploying contracts to a public testnet.

---

If you want, I can also create `contract.sol` in the `Assignment 2` folder and add sample screenshots placeholders now.