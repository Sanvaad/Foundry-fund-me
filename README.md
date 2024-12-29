```markdown
# FundMe Smart Contract

A Solidity-based decentralized funding contract that utilizes Chainlink price feeds to enable secure and accurate funding in ETH. This contract allows users to contribute ETH, tracks contributions, and supports secure withdrawal of funds by the contract owner.

## Features

- **Decentralized Funding:** Users can send ETH to the contract, which ensures the value meets a minimum USD threshold using Chainlink price feeds.
- **Accurate Price Conversion:** The contract uses Chainlink's `AggregatorV3Interface` for real-time ETH/USD price conversion.
- **Secure Withdrawals:** Only the contract owner can withdraw funds.
- **Optimized Gas Usage:** Includes a `cheaperWithdraw` function to reduce gas costs.

---

## Project Structure

```plaintext
.
├── contracts
│   ├── FundMe.sol              # Main funding contract
│   ├── PriceConverter.sol      # Library for ETH to USD conversion
│   └── MockV3Aggregator.sol    # Mock Chainlink price feed for testing
├── script
│   ├── DeployFundMe.s.sol      # Deployment script for FundMe contract
│   ├── HelperConfig.s.sol      # Configuration for price feed and network-specific data
│   ├── Interactions.s.sol      # Scripts for interacting with FundMe
├── test
│   ├── InteractionsTest.sol    # Test suite for user interaction
│   └── FundMeTest.sol          # Unit tests for FundMe contract
├── README.md                   # Project documentation
└── .foundry.toml               # Foundry configuration
```

---

## Getting Started

### Prerequisites

- **Node.js and npm**: Install from [Node.js](https://nodejs.org/)
- **Foundry**: Install Foundry by following the [installation guide](https://book.getfoundry.sh/getting-started/installation).

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/fundme.git
   cd fundme
   ```

2. Install dependencies:
   ```bash
   forge install
   ```

---

## Usage

### Deploy the Contract

1. Deploy the `FundMe` contract using the deployment script:
   ```bash
   forge script script/DeployFundMe.s.sol --rpc-url <YOUR_RPC_URL> --private-key <YOUR_PRIVATE_KEY> --broadcast
   ```

### Interact with the Contract

- **Fund the Contract:**
   Call the `fund` function and send ETH to the contract. The ETH amount must meet the `MINIMUM_USD` threshold in USD value.

- **Withdraw Funds:**
   Only the owner of the contract can call the `withdraw` or `cheaperWithdraw` functions to retrieve funds.

---

## Tests

Run tests to ensure the contract behaves as expected:

```bash
forge test
```

### Test Coverage
- **`testUserCanFundAndOwnerWithdraw`:** Simulates funding and withdrawal interactions.
- **Unit Tests:** Cover all getter functions, price conversion logic, and owner-only restrictions.

---

## Configuration

### Chainlink Price Feed

The contract requires a Chainlink price feed address for deployment. Update the address in the deployment script or the `HelperConfig` file based on your network.

---

## Security

- **Owner Restriction:** Only the contract owner can withdraw funds.
- **Price Validation:** Funds are only accepted if they meet the USD threshold, ensuring accurate contributions.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- [Chainlink](https://chain.link/) for decentralized price feeds.
- [Patrick Collins](https://github.com/PatrickAlphaC) for inspiration and educational resources.

---

## Contributing

Contributions are welcome! Please open an issue or pull request for suggestions or improvements.

---

## Contact

Feel free to reach out:

- **Email:** houseofsanvaad@gmail.com
- **GitHub:** [sanvaad](https://github.com/sanvaad)

```

Replace placeholders like `<YOUR_RPC_URL>`, `<YOUR_PRIVATE_KEY>`, and contact information with your actual details. Let me know if you’d like additional customization!
