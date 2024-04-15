## MEV Templates in Python, JavaScript, and Rust

These three MEV templates are designed for readability and adhere to a consistent design pattern, enabling the replication of prevalent MEV strategies such as sandwich, frontrunning, arbitrage, and sniping.

### Included Example: DEX Flashloan Arbitrage

Each template features a **DEX flashloan arbitrage example** to demonstrate usage. This example, while functional, requires further adjustments, particularly in terms of order size optimization and gas bidding strategies, to operate effectively as a DEX arbitrage bot. The operational steps include:

1. **Retrieving Historical Events**: Fetch all historical events from the blockchain (`PairCreated`).
2. **Constructing Arbitrage Paths**: Create a triangular arbitrage path using the pools retrieved.
3. **Multicall Requests**: Perform a multicall request of "getReserve" calls to all pools involved in trading (capable of retrieving data from over 6000 pools within 1-3 seconds).
4. **Streaming Data**: Stream new headers, pending transactions, and events asynchronously.
5. **Offline Simulation**: Simulate Uniswap V2 3-hop paths offline.
6. **Transaction Management**: Sign transactions and create bundles for submission to Flashbots; also supports sending transactions to the txpool (mempool).


## What is this?

![Professor Oak](https://github.com/solidquant/mev-templates/assets/134243834/553560de-3334-4d4b-a447-14aa91ad28de)

> (Professor Oak) *Good. So you are here.*

In this Github repository, you can pick one of the most popular languages to use in your MEV project. By studying this project, you'll get a feel for how MEV strategies are built.

Most strategies share a common code base, and this repository is an attempt to include the basic tooling required for all level of traders to have in their pockets.

---

## How should I use this?

Running the templates provided here are straightforward, however, you do need to create a .env file before you can begin:

- **HTTPS_URL**: your node endpoints
- **WSS_URL**: your node endpoints
- **CHAIN_ID**: 1 if Ethereum, 137 if Polygon
- **BLOCKNATIVE_TOKEN**: this is for the gas estimator service from Blocknative, you can create an account there and get the API key
- **PRIVATE_KEY**: your real wallet key, what you have to protect with your life
- **SIGNING_KEY**: just a key used for Flashbots reputation/identity
- **BOT_ADDRESS**: the address of your bot contract (V2ArbBot)

You can use the provided .env.example file and create an exact copy and name it .env (sample below):

```
HTTPS_URL=http://192.168.200.182:8545
WSS_URL=ws://192.168.200.182:8546
CHAIN_ID=137
BLOCKNATIVE_TOKEN=<token-here>

PRIVATE_KEY=0xb3e5dc08b18918cce982438a28877e440aafc01fef4c314b95d0609bf946585f
SIGNING_KEY=0x34f55bef77aca52be9f7506da40205f8ecd7e863fd3b465a5db9950247422caf
BOT_ADDRESS=0xEc1f2DADF368D5a20D494a2974bC19e421812017
```

---

## Benchmarks

It's always difficult to pick a programming language just right for the task, and often times, it shouldn't really matter what language you use. We should take many factors into account and decide on the one that you feel most comfortable with.

Among these factors, we should consider how fast each language is - in an environment that's similar to how most people would use the language, not in a super optimized way, because we don't normally hyper-optimize our codes.

For this reason, I've run few benchmarks of the three templates to see how fast each can go.

[📊 Checkout the results from this blog post](https://medium.com/@solidquant/how-fast-is-your-mev-bot-comparing-javascript-python-rust-72376a820291)

---

You can find more about this project in my blog post:

[👉 MEV templates written in Python, Javascript, and Rust](https://medium.com/@solidquant/mev-templates-written-in-python-javascript-and-rust-ddd3d324d709)

⚡️ Plus, come join our Discord community to take this journey together. We’re actively reviewing the code used in these blog posts to guarantee safe usage by all our members. Though still in its infancy, we’re slowly growing and collaborating on research/projects in the 💫 MEV space 🏄‍♀️🏄‍♂️:

[👨‍👩‍👦‍👦 Join the Solid Quant Discord Server!](https://discord.com/invite/e6KpjTQP98)

Also, for people that want to reach out to me, they can e-mail me directly at: solidquant@gmail.com
