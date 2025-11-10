# DAO

<!-- <div align="center">
  <a href="https://github.com/Ramprasad4121/dao">
    <img src="docs/images/dao-banner.png" alt="DAO Banner" width="600" height="300">
  </a>
</div> -->

<div align="center">
  Decentralized Autonomous Organization with Governance
  <br />
  <a href="#about"><strong>Explore the demo »</strong></a>
  <br />
  <br />
  <a href="https://github.com/Ramprasad4121/dao/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/Ramprasad4121/dao/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
  ·
  <a href="https://github.com/Ramprasad4121/dao/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+">Ask a Question</a>
</div>

<div align="center">
<br />

[![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-blue)](https://soliditylang.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

</div>

<details open="open">
<summary>Table of Contents</summary>

- [DAO](#dao)
  - [About](#about)
    - [Built With](#built-with)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
    - [Local Development](#local-development)
    - [Testnet (Sepolia)](#testnet-sepolia)
    - [Interactions](#interactions)
    - [Testing](#testing)
    - [Other Commands](#other-commands)
  - [Roadmap](#roadmap)
  - [Support](#support)
  - [Project Assistance](#project-assistance)
  - [Contributing](#contributing)
  - [Authors \& Contributors](#authors--contributors)
  - [Security](#security)
  - [License](#license)
  - [Acknowledgements](#acknowledgements)

</details>

---

## About

Governance DAO using OpenZeppelin Governor for proposal creation, voting with ERC-20 tokens, and execution. Supports quorum, timelocks, and delegation. Built with Foundry for comprehensive testing and deployment to Anvil or Sepolia.

Why this? To enable community-driven decision-making in DeFi with secure, auditable contracts.

<!-- <details>
<summary>Screenshots</summary>
<br>

|                               Local Deployment Console                               |                               Proposal Voting Simulation                               |
| :-------------------------------------------------------------------: | :--------------------------------------------------------------------: |
| <img src="docs/images/deploy-local.png" title="Anvil Deployment" width="100%"> | <img src="docs/images/vote-sim.png" title="Voting Test" width="100%"> |

> Add screenshots of `make deploy` and `forge test` outputs.

</details> -->

### Built With

- [Foundry](https://book.getfoundry.sh/) – Forge, Cast, Anvil
- [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts) – Governor, ERC-20
- Solidity ^0.8.20
- [Make](https://www.gnu.org/software/make/) – Automation

## Getting Started

### Prerequisites

- Git (`git --version`)
- Foundry (`curl -L https://foundry.paradigm.xyz | bash && foundryup`; `forge --version`)

### Installation

1. Clone:
   ```bash
   git clone https://github.com/Ramprasad4121/dao.git
   cd dao
   ```

2. Build:
   ```bash
   forge build
   ```

3. Setup `.env` from `.env.example`: Add `SEPOLIA_RPC_URL`, `PRIVATE_KEY` (test only), `ETHERSCAN_API_KEY` (optional).

## Usage

### Local Development

- Start Anvil:
  ```bash
  make anvil
  ```

- Deploy:
  ```bash
  make deploy
  ```

### Testnet (Sepolia)

1. Fund: [Sepolia Faucet](https://sepoliafaucet.com/).
2. Deploy:
   ```bash
   make deploy ARGS="--network sepolia"
   ```

### Interactions

- Delegate tokens:
  ```bash
  cast send <GOVERNOR_ADDRESS> "delegate(address)" <DELEGATE> --private-key $PRIVATE_KEY --rpc-url $SEPOLIA_RPC_URL
  ```

- Propose:
  ```bash
  cast send <GOVERNOR_ADDRESS> "propose(address[],uint256[],bytes[])" "[<TARGET>]" "[<VALUE>]" "[<CALLDATA>]" --private-key $PRIVATE_KEY --rpc-url $SEPOLIA_RPC_URL
  ```

- Vote:
  ```bash
  cast send <GOVERNOR_ADDRESS> "castVote(uint256,uint8)" <PROPOSAL_ID> <SUPPORT> --private-key $PRIVATE_KEY --rpc-url $SEPOLIA_RPC_URL
  ```

### Testing

- Unit:
  ```bash
  forge test
  ```

- Coverage:
  ```bash
  forge coverage --report lcov
  ```

### Other Commands

- Format: `forge fmt`
- Gas: `forge snapshot`
- Clean: `make clean`

## Roadmap

[Open issues](https://github.com/Ramprasad4121/dao/issues).

- Enhancements: Multisig, treasury
- Bugs: Vote with 👍

Future: Frontend dashboard.

## Support

- [Issues](https://github.com/Ramprasad4121/dao/issues/new?assignees=&labels=question&template=04_SUPPORT_QUESTION.md&title=support%3A+)
- [X](https://x.com/0xramprasad)

## Project Assistance

- ⭐ [Star](https://github.com/Ramprasad4121/dao)
- Tweet: "#DAO #Governance"
- Blog: [Dev.to](https://dev.to/)

## Contributing

Fork, branch (`git checkout -b feature/xyz`), commit, PR. See [CONTRIBUTING.md](docs/CONTRIBUTING.md).

## Authors & Contributors

- [Ramprasad4121](https://github.com/Ramprasad4121)

[Contributors](https://github.com/Ramprasad4121/dao/contributors)

## Security

Timelock-secured; audit proposals. Report: [SECURITY.md](docs/SECURITY.md). "As is."

## License

MIT License. See [LICENSE](LICENSE).

## Acknowledgements

- [OpenZeppelin](https://openzeppelin.com/) – Governance
- [Foundry](https://getfoundry.sh/) – Toolkit
- Ethereum DAO community.