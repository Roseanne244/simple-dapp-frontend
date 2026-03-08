# 🌐 Simple DApp Frontend — RoseCoin

A minimal Web3 DApp frontend that connects to MetaMask and interacts with the RoseCoin (RSC) ERC-20 token on Sepolia Testnet.

Built with plain HTML, CSS, and ethers.js — no frameworks needed.

---

## 🖥️ Live Demo

> Open `index.html` directly in your browser — no server required!

---

## ✨ Features

- 🦊 Connect MetaMask wallet
- 👁️ View your RSC token balance
- 📊 View total token supply
- ➤ Transfer RSC to any address
- ✅ Transaction status feedback (pending, success, error)
- 📱 Responsive UI

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| HTML / CSS / JS | Frontend |
| [ethers.js v6](https://ethers.org) | Interact with blockchain |
| [MetaMask](https://metamask.io) | Wallet & signing |
| Sepolia Testnet | Test blockchain |

---

## 🚀 How to Use

### 1. Prerequisites
- Install [MetaMask](https://metamask.io) browser extension
- Add Sepolia Testnet to MetaMask
- Get free test ETH from [sepoliafaucet.com](https://sepoliafaucet.com)

### 2. Configure the contract address
Open `index.html` and find this line:
```javascript
const CONTRACT_ADDRESS = "0xYOUR_CONTRACT_ADDRESS_HERE";
```
Replace with the deployed RoseCoin contract address from the [erc20-token](../2-erc20-token/) repo.

### 3. Open the app
Simply open `index.html` in your browser (Chrome or Firefox with MetaMask).

### 4. Connect & transact
1. Click **Connect MetaMask**
2. Approve the connection in MetaMask
3. View your balance
4. Send RSC tokens!

---

## 📁 Project Structure

```
simple-dapp-frontend/
│
├── index.html     # Main app (HTML + CSS + JS all in one file)
└── README.md
```

---

## 🔑 Key Code Concepts

**Connect wallet:**
```javascript
const provider = new ethers.BrowserProvider(window.ethereum);
const signer = await provider.getSigner();
```

**Read from contract (free):**
```javascript
const balance = await contract.balanceOf(userAddress);
```

**Write to contract (costs gas):**
```javascript
const tx = await contract.transfer(recipient, ethers.parseEther("100"));
await tx.wait(); // Wait for block confirmation
```

---

## 📚 What I Learned

- How to connect a frontend to MetaMask using ethers.js
- Difference between `provider` (read) and `signer` (write)
- How to call read functions vs write (state-changing) functions
- Handling async transactions and waiting for confirmations
- ABI — the bridge between frontend and smart contract

---

## 📄 License

MIT
