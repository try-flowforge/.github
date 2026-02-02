<div align="center">
  <a href="https://www.github.com/try-flowforge/">
    <img src="https://raw.githubusercontent.com/try-flowforge/.github/main/assets/logo.svg" alt="FlowForge">
  </a>
</div>

<h3 align="center">Built for <a href="https://ethglobal.com/events/hackmoney2026">@ETHGlobal</a> HackMoney 2026 Submission.</h3>

---

## Overview

FlowForge is a system that lets you design and run automated workflows connecting **Web2 services** (APIs, webhooks, schedules) with **Web3 actions** (on-chain reads, swaps, lending, borrowing).

Instead of hard-coding automations, FlowForge uses **workflows**: reusable, visual sequences of steps that the system executes for you.

Workflows are modelled as a **directed graph** of steps (called *nodes*) connected by *edges* that define execution order and data flow. This makes automations easier to reason about, replay, debug, and evolve over time.

---

## Who Is It For?

FlowForge is designed for teams who need reliable and composable automation across Web2 and Web3:

- **Crypto / DeFi teams** automating trading, rebalancing, lending/borrowing, or treasury operations  
- **Fintech and data teams** building price-driven logic using on-chain data  
- **Ops and engineering teams** looking for a single orchestration layer instead of custom scripts and cron jobs  

You don’t need to be a low-level blockchain engineer, but familiarity with DeFi concepts (swaps, wallets, gas, lending) is recommended.

---

## Core Concepts

### Workflow

A complete automation, such as:

- “Every hour, swap USDC to WETH”
- “If ETH price > X, move funds into lending”

### Node

A single step in a workflow. Common node types include:

- **Trigger**
  - Schedule (cron-like)
  - Manual (on demand)
  - Webhook / API event
- **Swap**
  - Trade tokens via aggregators (Uniswap, Relay, 1inch)
- **Lending / Borrowing**
  - Interact with protocols like Aave or Compound
- **Price Oracle**
  - Fetch prices from Chainlink or Pyth
- **Logic / Conditions**
  - IF / THEN branching based on data
- **Web2 / API**
  - Call external APIs, webhooks, or send notifications

### Edge

Defines the execution order and data flow between nodes.

### Wallet

The on-chain address that:

- Holds funds
- Signs and submits transactions

### Network

Supported blockchain networks where workflows run, such as:

- Arbitrum One Mainnet
- Arbitrum Sepolia Testnet
- Ethereum Sepolia Testnet

---

## What Problems It Solves

### Automated DeFi Operations

- Periodic swaps (DCA strategies, treasury rebalancing)
- Automated collateral management
- Chaining oracle checks with on-chain actions

### Reliable Price-Driven Logic

- Fetch prices from trusted oracles (Chainlink, Pyth)
- Trigger actions based on market conditions
- Standardise how price data is used across workflows

### Unified Web2 + Web3 Automation

- Start workflows via schedules or webhooks
- Combine off-chain events with on-chain actions
- Replace scattered scripts and cron jobs with a single system

---

## How It Works

### 1. Define a Workflow in the UI

You specify:

- A workflow name (e.g., **“Hourly USDC → WETH DCA”**)
- A set of nodes and their connections
- Configuration for each node (tokens, amounts, oracle, conditions)
- How the workflow is triggered

### 2. Workflow Validation

The system checks:

- All nodes are connected in a valid execution order
- No infinite loops exist
- Required configuration (wallets, token addresses, networks) is present

### 3. Execution

When triggered:

- A scheduler or external event starts the workflow
- The engine executes nodes sequentially:
  - Fetching data (e.g., prices)
  - Evaluating conditions
  - Sending on-chain transactions when rules are met

### 4. Observability & Replay

- Each run produces a full execution trace
- Inputs and outputs of every node are recorded
- Failed steps can be inspected, debugged, or replayed

---

## Key Capabilities

### DeFi Integrations

- Token swaps via Uniswap, Relay, and 1inch
- Lending & borrowing through Aave V3 and Compound V3
- Support for Arbitrum mainnet and test networks

### Price Oracles

- Chainlink and Pyth price feeds
- Use oracle data directly in workflow conditions

### Triggers & Scheduling

- Run workflows:
  - On a fixed schedule
  - On demand via UI or API
  - In response to external webhooks or events

### Conditional Logic

- Build IF / THEN logic into workflows:
  - IF price > threshold → execute swap
  - IF balance exceeds X → lend excess
  - IF oracle call fails → retry or notify

### Extensibility

- Add new node types without redesigning workflows
- Clone and adapt existing workflows for new strategies
- Future support for advanced nodes (AI/LLM, richer Web2 integrations, flow control)

---

## Typical Use Cases

### Treasury Management

- Automatic portfolio rebalancing
- Downside protection via price-based rules
- Lending idle assets to earn yield

### Trading & Market-Making

- Rule-based strategies driven by oracle data
- Chained swaps with conditional execution

### Monitoring & Alerting

- Periodic checks on prices or positions
- Trigger notifications, hedging trades, or rebalancing

### Research & Prototyping

- Rapid experimentation on testnets
- Iterate on logic without writing low-level blockchain code

---

## Status

FlowForge is under active development. Features and integrations will continue to evolve.
