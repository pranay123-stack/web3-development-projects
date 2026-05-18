# Web3 Development Projects

A curated collection of Web3, blockchain, and decentralized application (dApp) projects — from foundational smart contracts to full-stack DeFi protocols. Built for learning, experimentation, and real-world deployment.

---

## Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Projects](#projects)
  - [Beginner](#beginner)
  - [Intermediate](#intermediate)
  - [Advanced](#advanced)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [Deployment](#deployment)
- [Security Considerations](#security-considerations)
- [Resources](#resources)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This repository is a progressive collection of Web3 projects designed to take you from writing your first Solidity contract to building production-grade decentralized applications. Each project is self-contained with its own documentation, tests, and deployment scripts.

**What you'll find here:**

- Smart contracts written in Solidity (and some in Vyper)
- Full-stack dApps with React/Next.js frontends
- DeFi protocols: lending, staking, AMMs, vaults
- NFT projects: minting, marketplaces, dynamic NFTs
- Cross-chain and Layer 2 integrations
- DAO governance systems
- Oracle integrations and off-chain data handling

---

## Tech Stack

| Layer          | Technology                                      |
| -------------- | ----------------------------------------------- |
| Smart Contracts | Solidity, Vyper                                |
| Frameworks     | Hardhat, Foundry                                |
| Frontend       | React, Next.js, ethers.js, wagmi, viem          |
| Testing        | Chai, Mocha, Foundry Forge tests                |
| Deployment     | Hardhat Ignition, Foundry scripts               |
| Networks       | Ethereum, Polygon, Arbitrum, Base, Sepolia      |
| Storage        | IPFS, Arweave                                   |
| Indexing       | The Graph, Alchemy                              |
| Wallets        | MetaMask, WalletConnect, RainbowKit             |

---

## Projects

### Beginner

| #  | Project                        | Description                                              |
| -- | ------------------------------ | -------------------------------------------------------- |
| 01 | **Hello Blockchain**           | Simple storage contract — read/write state on-chain      |
| 02 | **ERC-20 Token**               | Create and deploy a custom fungible token                |
| 03 | **ERC-721 NFT**                | Mint NFTs with metadata stored on IPFS                   |
| 04 | **Ether Wallet**               | Basic wallet contract with deposit/withdraw functions     |
| 05 | **Crowdfunding**               | Time-bound fundraising with refund mechanism              |

### Intermediate

| #  | Project                        | Description                                              |
| -- | ------------------------------ | -------------------------------------------------------- |
| 06 | **DEX (Decentralized Exchange)** | Constant-product AMM inspired by Uniswap V2            |
| 07 | **Staking Platform**           | Stake ERC-20 tokens and earn yield over time             |
| 08 | **NFT Marketplace**            | List, buy, sell, and auction NFTs with royalty support    |
| 09 | **Multi-Sig Wallet**           | N-of-M approval wallet for treasury management           |
| 10 | **DAO Governance**             | On-chain proposal creation, voting, and execution        |

### Advanced

| #  | Project                        | Description                                              |
| -- | ------------------------------ | -------------------------------------------------------- |
| 11 | **Lending Protocol**           | Collateralized lending/borrowing with liquidation engine  |
| 12 | **Yield Aggregator (Vault)**   | Auto-compounding vault strategy across DeFi protocols    |
| 13 | **Cross-Chain Bridge**         | Lock-and-mint bridge between L1 and L2 networks          |
| 14 | **Flash Loan Arbitrage**       | Atomic arbitrage using flash loans across DEXs           |
| 15 | **Upgradeable Proxy Contracts**| UUPS and Transparent proxy patterns for upgradeability    |

---

## Repository Structure

```
web3-development-projects/
├── 01-hello-blockchain/
│   ├── contracts/
│   ├── test/
│   ├── scripts/
│   ├── hardhat.config.js
│   └── README.md
├── 02-erc20-token/
│   ├── contracts/
│   ├── test/
│   ├── scripts/
│   └── README.md
├── ...
├── foundry-projects/          # Projects using Foundry framework
│   ├── src/
│   ├── test/
│   └── script/
├── frontend/                  # Shared frontend templates
│   ├── components/
│   ├── hooks/
│   └── utils/
├── shared/                    # Shared utilities and helpers
│   ├── deploy-helpers.js
│   └── constants.js
└── README.md
```

Each project directory is self-contained and can be run independently.

---

## Getting Started

### Prerequisites

- **Node.js** >= 18.x
- **npm** or **yarn** or **pnpm**
- **Git**
- **MetaMask** browser extension (for interacting with dApps)

### Installation

```bash
# Clone the repository
git clone https://github.com/pranay123-stack/web3-development-projects.git
cd web3-development-projects

# Navigate to any project
cd 01-hello-blockchain

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Add your private key and RPC URLs to .env
```

### Environment Variables

Each project expects a `.env` file with:

```env
PRIVATE_KEY=your_wallet_private_key
SEPOLIA_RPC_URL=https://eth-sepolia.g.alchemy.com/v2/YOUR_KEY
ETHERSCAN_API_KEY=your_etherscan_api_key
```

> **Warning:** Never commit your `.env` file. All projects include `.gitignore` with `.env` excluded.

---

## Development Workflow

### Using Hardhat

```bash
# Compile contracts
npx hardhat compile

# Run local node
npx hardhat node

# Deploy to local network
npx hardhat run scripts/deploy.js --network localhost

# Deploy to testnet
npx hardhat run scripts/deploy.js --network sepolia
```

### Using Foundry

```bash
# Build
forge build

# Run tests
forge test -vvv

# Deploy
forge script script/Deploy.s.sol --rpc-url $SEPOLIA_RPC_URL --broadcast
```

---

## Testing

Every project includes comprehensive tests covering:

- **Unit tests** — individual function behavior
- **Integration tests** — contract interactions
- **Fuzz tests** — randomized input testing (Foundry)
- **Fork tests** — testing against mainnet state

```bash
# Hardhat tests
npx hardhat test

# Hardhat coverage
npx hardhat coverage

# Foundry tests with verbosity
forge test -vvv

# Foundry gas report
forge test --gas-report
```

---

## Deployment

### Supported Networks

| Network      | Chain ID | Type      |
| ------------ | -------- | --------- |
| Ethereum     | 1        | Mainnet   |
| Sepolia      | 11155111 | Testnet   |
| Polygon      | 137      | Mainnet   |
| Mumbai       | 80001    | Testnet   |
| Arbitrum One | 42161    | L2        |
| Base         | 8453     | L2        |

### Contract Verification

```bash
# Verify on Etherscan after deployment
npx hardhat verify --network sepolia DEPLOYED_ADDRESS "constructor_arg1" "constructor_arg2"
```

---

## Security Considerations

- All contracts follow [OpenZeppelin](https://docs.openzeppelin.com/) best practices
- Reentrancy guards applied using `ReentrancyGuard`
- Access control via `Ownable` and `AccessControl`
- Integer overflow protection (Solidity >= 0.8.0)
- Projects are for **educational purposes** — audit thoroughly before any mainnet deployment with real funds
- Never hardcode private keys or secrets in source code

---

## Resources

**Documentation & Guides:**
- [Solidity Docs](https://docs.soliditylang.org/)
- [Hardhat Documentation](https://hardhat.org/docs)
- [Foundry Book](https://book.getfoundry.sh/)
- [OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/)
- [Ethereum Developer Resources](https://ethereum.org/developers)

**Learning Platforms:**
- [CryptoZombies](https://cryptozombies.io/) — Interactive Solidity tutorials
- [Speedrun Ethereum](https://speedrunethereum.com/) — Build and ship dApps
- [Alchemy University](https://www.alchemy.com/university) — Full Web3 bootcamp

**Security:**
- [Slither](https://github.com/crytic/slither) — Static analysis framework
- [Mythril](https://github.com/Consensys/mythril) — Security analysis tool
- [Damn Vulnerable DeFi](https://www.damnvulnerabledefi.xyz/) — Security challenges

---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-project`)
3. Write your code with tests
4. Ensure all tests pass
5. Submit a pull request with a clear description

Please follow the existing project structure and include a `README.md` in each new project directory.

---

## License

This repository is licensed under the [MIT License](LICENSE).

---

**Built with curiosity and coffee.** If you find this useful, consider giving it a star.
