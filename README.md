# Fund-Me-Contract-

Support for Multiple Currencies in FundMe Contract

Introduction

With the rapid growth of blockchain technology and the rise of decentralized finance (DeFi), supporting multiple digital currencies has become essential. Allowing users to contribute using their preferred currency expands your app’s reach and improves overall usability.

In this contract, you'll add currency conversion to the FundMe contract using Chainlink Oracles, and set dynamic price thresholds in USD.


---

USD Price Validation

By default, the FundMe contract only accepts contributions greater than 1 ETH. To improve accessibility, we change that to $5 USD.

We Start by adding the following state variable:

uint256 public minimumUSD = 5;

Next, update the logic in the fund() function to ensure the ETH value sent is equivalent to or exceeds $5 USD. But there's a challenge: ETH is on-chain, and USD is off-chain.


---

The Oracle Problem

ETH/USD exchange rates are determined by real-world financial markets—not by the blockchain. Blockchain's deterministic nature prevents direct access to off-chain data, creating what's known as the Oracle Problem.

To enable smart contracts to interact with real-world data securely, a decentralized Oracle network is required. Enter Chainlink.


---

Why Chainlink?

Using a centralized oracle introduces a single point of failure and undermines decentralization. Chainlink solves this by providing a modular, decentralized Oracle Network, empowering smart contracts with:

Real-time market data

Automation

Secure random number generation

External API calls



---

Key Chainlink Features

1. Data Feeds

Chainlink Data Feeds are used across DeFi to fetch reliable price data. A network of nodes aggregates and verifies prices from multiple sources, delivering them to on-chain price feed contracts. These feeds power over $50B in DeFi applications.

2. Verifiable Random Function (VRF)

Chainlink VRF provides tamper-proof randomness for use cases like:

NFT minting

Lotteries

Blockchain gaming


3. Automation (Keepers)

Chainlink Automation (formerly Keepers) lets you automate smart contract functions by listening for on-chain events and executing actions based on triggers.

4. Chainlink Functions

Chainlink Functions allow smart contracts to call any external API in a decentralized way. Ideal for advanced, real-world integrated applications.


---

Conclusion

By integrating Chainlink Data Feeds, we can perform accurate currency conversions in our FundMe contract and safely accept user contributions in USD value equivalents. Chainlink not only solves the Oracle Problem, but also adds powerful features to build truly dynamic, feature-rich dApps.
