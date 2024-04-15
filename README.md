## MEV Templates in Python, JavaScript, and Rust

These MEV templates are crafted for clarity and consistency, facilitating the replication of common MEV strategies like sandwich, frontrunning, arbitrage, and sniping.

### Example Included: DEX Flashloan Arbitrage

Each template includes a **DEX flashloan arbitrage example** demonstrating the practical application. This basic example requires additional fine-tuning, particularly in optimizing order sizes and gas bidding strategies, to function effectively as a DEX arbitrage bot. The steps involved are:

1. **Retrieving Historical Events**: Fetch all historical events from the blockchain (`PairCreated`).
2. **Constructing Arbitrage Paths**: Create a triangular arbitrage path from the retrieved pools.
3. **Multicall Requests**: Execute a multicall of "getReserve" requests to all involved trading pools (handling over 6000 pools in 1-3 seconds).
4. **Streaming Data**: Stream new headers, pending transactions, and events asynchronously.
5. **Offline Simulation**: Simulate Uniswap V2 3-hop paths offline.
6. **Transaction Management**: Sign transactions and bundle for submission to Flashbots; also supports sending transactions to the mempool.

## Introduction

![Professor Oak](https://github.com/solidquant/mev-templates/assets/134243834/553560de-3334-4d4b-a447-14aa91ad28de)

> (Professor Oak) *Good. So you are here.*

This repository offers MEV templates in popular programming languages. It serves as a foundation for understanding and developing MEV strategies, equipped with basic tooling essential for traders at all levels.

## Setup Instructions

To run these templates, you need to configure environment variables in a .env file:

- **HTTPS_URL**: Your node endpoints
- **WSS_URL**: Your node endpoints
- **CHAIN_ID**: Set to 1 for Ethereum, 137 for Polygon
- **BLOCKNATIVE_TOKEN**: API key from Blocknative for the gas estimator service; you can get one at Block naitive.
- **PRIVATE_KEY**: Your critical wallet key
- **SIGNING_KEY**: Key used for Flashbots reputation/identity
- **BOT_ADDRESS**: Address of your bot contract (V2ArbBot)

Use the provided `.env.example` as a template. Rename the copied file to `.env` with your specific settings:

```plaintext
HTTPS_URL=http://192.168.200.182:8545
WSS_URL=ws://192.168.200.182:8546
CHAIN_ID=137
BLOCKNATIVE_TOKEN=<token-here>
PRIVATE_KEY=0xb3e5dc08b18918cce982438a28877e440aafc01fef4c314b95d0609bf946585f
SIGNING_KEY=0x34f55bef77aca52be9f7506da40205f8ecd7e863fd3b465a5db9950247422caf
BOT_ADDRESS=0xEc1f2DADF368D5a20D494a2974bC19e421812017
```

## Benchmarks

Choosing the right programming language is crucial. While many factors should be considered, ease of use and execution speed are paramount.

I've benchmarked the templates to evaluate their performance. Details are available in this blog post:

[📊 Checkout the results from this blog post](https://medium.com/@solidquant/how-fast-is-your-mev-bot-comparing-javascript-python-rust-72376a820291)

---

You can find more about this project in my blog post:

[👉 MEV templates written in Python, Javascript, and Rust](https://medium.com/@solidquant/mev-templates-written-in-python-javascript-and-rust-ddd3d324d709)

⚡️ Plus, come join our Discord community to take this journey together. We’re actively reviewing the code used in these blog posts to guarantee safe usage by all our members. Though still in its infancy, we’re slowly growing and collaborating on research/projects in the 💫 MEV space 🏄‍♀️🏄‍♂️:

[👨‍👩‍👦‍👦 Join the Solid Quant Discord Server!](https://discord.com/invite/e6KpjTQP98)

Also, for people that want to reach out to me, they can e-mail me directly at: solidquant@gmail.com
