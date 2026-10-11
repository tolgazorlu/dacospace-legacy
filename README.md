<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<div align="center">
  <a href="#">
    <img style="border-radius: 10px" src="/daco-logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">DACOSPACE</h3>
  <p align="center">
    Daily learning content platform, paid for with EDU tokens on Open Campus
  </p>
</div>

## About The Project

**Daily Contents: Elevate Your Learning Experience!**
Dacospace lets learners purchase courses with EDU tokens on the Open Campus / EduChain network. Once enrolled, learners get daily lessons released one step at a time instead of the whole course at once, which keeps progress structured and avoids overwhelming a beginner. Built 2024-08 to 2024-12.

## Features

- React client with course listing, enrollment and a daily-lesson view (`client/src`)
- Wallet connect and on-chain enrollment via Open Campus OCID Connect
- Solidity contract (`contracts/src/Dacospace.sol`) handling course purchase/enrollment, deployed with Foundry to the Open Campus Codex testnet

## Tech Stack

- **Client:** React, TypeScript, Vite, TailwindCSS, DaisyUI, React Query, React Router, Viem/Web3.js
- **Contracts:** Solidity, Foundry

## Project Structure

```
client/     React + Vite frontend
contracts/  Foundry project: Dacospace.sol contract, deploy script
```

## Getting Started

### Prerequisites

- npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/tolgazorlu/dacospace-legacy.git
   ```
2. Install client packages
   ```sh
   cd client
   npm install
   npm run dev
   ```
3. Compile and deploy contracts
   ```sh
   cd contracts
   forge install
   forge compile

   forge script script/DeployDacospace.s.sol --broadcast --rpc-url https://rpc.open-campus-codex.gelato.digital/ --gas-limit 30000000 --with-gas-price 5gwei --skip-simulation

   forge verify-contract \
   --rpc-url https://rpc.open-campus-codex.gelato.digital \
   --verifier blockscout \
   --verifier-url 'https://opencampus-codex.blockscout.com/api/' \
   <your address> \
   src/Dacospace.sol:Dacospace
   ```

   Copy `contracts/.env.example` to `contracts/.env` and fill in the required keys before deploying.

## Status

Archived: superseded by dacospace.

## License

See [LICENSE.md](./LICENSE.md).

## Contact

Tolga Zorlu - [@linkedin](https://www.linkedin.com/in/tolgazorlu/)
