# 🏛️ DAO Smart Contract Project

## 📌 Overview

A simple DAO (Decentralized Autonomous Organization) implemented in Solidity that allows members to create proposals, vote, and execute decisions without a central authority. The contract demonstrates basic DAO primitives: member management, proposal lifecycle, voting and execution.

---

## ⚙️ Features

- Add voters
- Create proposals
- Vote (one vote per member)
- Execute proposals after deadline

---

## 🧠 Voting Mechanism

- Only members can vote
- One vote per proposal
- Voting allowed before deadline
- Proposal passes if it gets votes

---

## 📝 Proposal Creation

- Only members can create proposals
- Each proposal includes: description, vote count, deadline, and execution status

---

## 🔄 Workflow

Deploy → Add Members → Create Proposal → Vote → Execute

---

## 🛠️ Tools

- Solidity
- Remix IDE
- MetaMask
- Sepolia Testnet

---

## 🚀 How to Run

1. Open [DAO.sol](DAO.sol) in Remix (or paste the contract into the Remix editor).
2. Compile using a 0.8.x Solidity compiler.
3. Connect MetaMask and select `Sepolia Testnet` (or chosen testnet).
4. Deploy the contract and use the `Deployed Contracts` UI to interact: add members, create proposals, vote, and execute proposals.

Notes:
- Use the `Low level interaction` section for quick manual calls (e.g., `addMember`, `createProposal`, `vote`, `executeProposal`, `getProposal`).

---

## 📸 Screenshots & Analysis

Below are the screenshots included in the `IMAGES/` folder with concise captions describing what each demonstrates.

- `IMAGES/Screenshot 2026-04-22 141835.png` — Remix `Deploy & Run` panel showing the contract compiled and deployed on Sepolia via MetaMask; verification messages from Sourcify/Blockscout are visible.
- `IMAGES/Screenshot 2026-04-22 141935.png` — Low-level interaction: `addMember(address)` was called with a member address and the transaction succeeded.
- `IMAGES/Screenshot 2026-04-22 142022.png` — `createProposal(string,uint256)` UI input populated (example: "New Proposal", deadline `120`) and the create transaction was mined successfully.
- `IMAGES/Screenshot 2026-04-22 142110.png` — `vote(uint256)` was called (proposal id `0`), transaction mined and execution completed, showing transaction details.
- `IMAGES/Screenshot 2026-04-22 142328.png` — `executeProposal(uint256)` call executed successfully and transaction mined (proposal execution step).
- `IMAGES/Screenshot 2026-04-22 142354.png` — `getProposal(uint256)` was used to read proposal data; the decoded output shows: description (`New Proposal`), vote count, deadline (unix/timestamp), and execution status `true`.

---

## 🎯 Conclusion

This project demonstrates how DAOs enable decentralized, transparent decision-making using smart contracts. The included screenshots trace a full lifecycle: deploy, add member, create proposal, vote, read proposal, and execute proposal.

---

## 📚 Reference

https://medium.com/@cromewar/decentralized-autonomous-organizations-a-step-by-step-guide-468c11179ced
