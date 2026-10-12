<!--
  Diwakar Matsa — GitHub profile README
  Theme: sleek minimal dark · accent #FF6B35 (ember) · bg #0D1117
  Header is badges only — no banner, no animated widgets.
-->

<p align="center">
  <a href="https://www.linkedin.com/in/diwakar-matsa-2a9733281">
    <img src="https://img.shields.io/badge/LinkedIn-Diwakar%20Matsa-FF6B35?style=flat&logo=linkedin&logoColor=white&labelColor=0D1117" alt="LinkedIn" />
  </a>
  <a href="mailto:void.00.diwakar@gmail.com">
    <img src="https://img.shields.io/badge/Email-void.00.diwakar-FF6B35?style=flat&logo=gmail&logoColor=white&labelColor=0D1117" alt="Email" />
  </a>
  <a href="https://github.com/21r21a33333?tab=repositories">
    <img src="https://img.shields.io/badge/Rust-first-FF6B35?style=flat&logo=rust&logoColor=white&labelColor=0D1117" alt="Rust-first" />
  </a>
  <a href="https://x.com/diwakr_matsa">
    <img src="https://img.shields.io/badge/X-@diwakr__matsa-FF6B35?style=flat&logo=x&logoColor=white&labelColor=0D1117" alt="X" />
  </a>
</p>

---

## About

I'm Diwakar — a **Blockchain & Backend Engineer** writing production **Rust** for Bitcoin, EVM, Solana and multi-chain systems where correctness and security aren't optional.

I work across the **cross-chain stack**, **applied cryptography**, **zero-knowledge** and **distributed systems**.

---

## What I'm building now

**Crypto SDE 1 @ [Garden Finance](https://garden.finance) — a Bitcoin R&D studio.**

I build production Rust across Garden's cross-chain stack — **relayers, indexers, and secure signing infrastructure** powering **trust-minimized settlement** over Bitcoin, EVM, and many other chains.

> Specifics are under NDA — the open-source work below is the same caliber.

**[Mercury](https://beta.trymercury.xyz) @ Unit Labs — your wealth, onchain.**

A **self-custodial brokerage for tokenized US equities on Solana**: hold stablecoins, invest in stocks, ETFs and curated baskets, and spend with the card — all from one wallet you actually control. Live in beta, and Unit Labs' submission to **Colosseum's Crypto World's Fair**.

---

## Deep dives

### 🔐 walletkit — safe EVM transaction infrastructure in Rust

Open-source · [github.com/21r21a33333/walletkit](https://github.com/21r21a33333/walletkit). One ergonomic Rust facade over [alloy](https://alloy.rs) that lets any dapp or backend send EVM transactions *safely*: keys that **never leave** a swappable signer backend, guardrails that **cannot be bypassed**, and a transaction lifecycle that survives stuck txs and reorgs. A client-side facade — **not** a custody service — where MPC/TEE signers, relayers, bundlers, paymasters and policy engines plug in behind narrow, object-safe traits (every layer is RPC-hoistable).

**Core guarantees**
- 🔑 **Signature-only keys** — no plaintext export; env / keystore / HD → KMS / HSM / Ledger / TEE / MPC as config swaps
- 🛡️ **Un-bypassable policy** — deny-over-allow rules gating *every* signature (tx, EIP-712, EIP-191, 7702); approved is provably what's signed
- 🔁 **Reliable lifecycle** — authoritative nonce manager, EIP-1559 gas bumps, a stable tx handle across bumps, reorg-aware confirmation
- 🧩 **Pluggable everything** — signer · policy · submission · nonce · gas · state, each behind a swappable trait

**Standards & protocols** *(implemented + roadmap)*

| Area | Standards |
| --- | --- |
| Signing | `EIP-712` · `EIP-191` · `EIP-2` low-s · `EIP-1271` / `ERC-6492` |
| Keys & gas | `EIP-2335` keystores · `BIP-44` HD · `EIP-1559` |
| Approvals | `Permit2` · `EIP-2612` · `EIP-3009` |
| Meta-tx & MEV | `ERC-2771` · Flashbots / MEV-Share |
| Account abstraction | `ERC-4337` (UserOp v0.6/0.7/0.8) · `ERC-7677` paymasters · `EIP-7702` · `ERC-7579` modules · `EIP-5792` |
| Privacy & intents | `ERC-5564` / `6538` stealth · `ERC-7683` cross-chain |
| Auth | `RIP-7212` secp256r1 passkeys |

**Integrates (never re-implements):** alloy signers · AWS KMS · Ledger / Trezor · Turnkey / Fireblocks / Web3Auth (MPC/TEE) · Safe{Core} multisig · Rundler / Silius / Alto bundlers · Pimlico / Alchemy / Gelato paymasters · Regorus (Rego/OPA) & WASM policy plugins · revm / Tenderly simulation · redb / SQLite state · eRPC.

### 🕶️ veil402 — a shielded pool that can still prove one transaction

[github.com/21r21a33333/veil402](https://github.com/21r21a33333/veil402) · A **zero-knowledge shielded UTXO pool on Solana** — Noir → Groth16 (Sunspot) → Anchor — hiding **amounts and recipients** in the Zcash / RAILGUN / Tornado-Nova lineage.

**Why 402.** Agentic payments settle on public rails, so an agent that pays its way through the world publishes your business as it runs — suppliers, prices, volume, timing.

**The fix:** pay shielded, then prove **one transaction** — `(value, asset, recipient)` — to **one chosen verifier**, bound and non-replayable, revealing nothing about any other. Not an all-or-nothing viewing key, not a global auditor key. Privacy by default, auditability on demand.

- 🔏 Noir circuit, Groth16 verified on-chain via CPI; audited against Tornado Nova & RAILGUN prior art
- 🌳 Append-only commitment tree, pool-scoped nullifier PDAs, reorg-safe state
- 🤖 Agent-payment SDK + demo — *roadmap*

> Research / active development — not audited, not for real funds.

---

## Tech

<p align="center">
  <img src="https://skillicons.dev/icons?i=rust,go,cpp,c,java,solidity,ts,py,nodejs,react,nextjs,postgres,mongodb,firebase,docker,aws,githubactions,linux&theme=dark&perline=9" alt="Tech stack" />
</p>

---

## Featured open-source

| Area | Project | What it is |
| --- | --- | --- |
| **Privacy & ZK** | [**veil402**](https://github.com/21r21a33333/veil402) | Shielded UTXO pool on Solana with per-transaction, per-verifier selective disclosure — Noir · Groth16 · Anchor |
| | [**openfhe-secure-maxcosine**](https://github.com/21r21a33333/openfhe-secure-maxcosine) | Maximum cosine similarity over *encrypted* vectors — OpenFHE CKKS, multiparty, no decryption |
| **Intents & execution** | [**solvent**](https://github.com/thesolvent/solvent) | Zero-inventory intent resolver on 1inch Aqua — fills UniswapX off non-custodial maker liquidity borrowed at settlement, holding no capital |
| | [**amm-rs**](https://github.com/21r21a33333/amm-rs) | Wei-exact AMM quoting library — Uniswap, Curve, Aerodrome, and your own pools |
| | [**arb-router**](https://github.com/21r21a33333/arb-router) | On-chain arbitrage-detection router — venue-agnostic engine over a pool graph |
| **Wallet & chain infra** | [**walletkit**](https://github.com/21r21a33333/walletkit) | One safe Rust facade over alloy for EVM tx sending — swappable signers, un-bypassable policy, reorg-safe lifecycle |
| | [**btc-tee-escrow**](https://github.com/21r21a33333/btc-tee-escrow) | Trustless Bitcoin escrow inside a TEE — enclave-compatible server, Bitcoin Script validation, provably-fair dispute resolution |
| | [**blockchain**](https://github.com/21r21a33333/blockchain) | Uniform Go clients for interacting with many different chains |
| **Products & tooling** | [**stockfront**](https://github.com/21r21a33333/stockfront) | Non-custodial income layer for tokenized stocks on BNB Chain — intent in, compiled and chain-validated strategy out |
| | [**ts-plugins-**](https://github.com/21r21a33333/ts-plugins-) | Contract-first, high-performance plugin infrastructure |
| | [**yt-notes**](https://github.com/21r21a33333/yt-notes) | Local pipeline turning any YouTube video into a structured note with frames, diagrams & timestamp links |
| | [**distributed-systems**](https://github.com/21r21a33333/distributed-systems) | Implementation techniques for engineering distributed systems |

**More** — [choose-rich](https://github.com/21r21a33333/choose-rich) · multi-chain gaming API • [interview-gpt-assistant](https://github.com/21r21a33333/interview-gpt-assistant) · LLM interview assistant • [alerts-notifier](https://github.com/21r21a33333/alerts-notifier) · Rust alert monitor with phone-call escalation

---

## Hackathons

### 🏆 Mercury — your wealth, onchain · Colosseum Crypto World's Fair

A **self-custodial brokerage for tokenized US equities on Solana**, built with Unit Labs and live in beta. Hold stablecoins, invest in stocks, ETFs and curated baskets, spend with the card — the simplicity of a modern financial account, without giving up custody.

- 💼 Stocks, ETFs and one-token diversified baskets, with cost-basis accounting that holds up
- ⚡ Solana execution — Jupiter routing, Kamino, wrapper selection per asset
- 📱 iOS app, web app and API in one monorepo, shipped to a public beta

<p>
  <a href="https://beta.trymercury.xyz"><b>Try the beta</b></a>
</p>

### 🏆 Stockfront — your AI prime broker for tokenized stocks · BNB Chain

State a financial intent — *"the safest way to earn yield on my stocks"* — and Stockfront recommends, compiles and prepares the optimal strategy against live chain state, sized to your holdings and signed by you. Non-custodial throughout; it composes existing protocols and deploys no contracts of its own.

- 🧠 Intent in, executable strategy out — carry, leverage and index exposure, each with its live rate shown before you commit
- 📉 Transparent risk — health factor before and after every borrow, liquidation distance, named risk per strategy
- 🔗 Venus, PancakeSwap V3, Reserve baskets and Glider folios, reached through Binance Web3
- 🦀 Rust backend (hexagonal core → adapters → app) with a React frontend · built with a teammate

<p>
  <a href="https://www.youtube.com/watch?v=a685OVbK_sY"><b>Demo video</b></a> ·
  <a href="https://github.com/21r21a33333/stockfront"><b>Code</b></a>
</p>

**Also built**

- **[Solvent](https://github.com/thesolvent/solvent)** · *ETHOnline 2026* — a zero-inventory, protocol-agnostic intent resolver on 1inch Aqua: one non-custodial maker balance backs solver inventory across many protocols at once, so the operator holds no capital and still keeps the spread.
- **[uniPay](https://github.com/TARS-Finance/uniPay)** · *Initia "Initiate" (DoraHacks)* — pay from any chain, settle and earn on Initia: customers pay in BTC, SOL or USDC on any major EVM, merchants receive USDC on Initia in ~30 seconds through trustless HTLC atomic swaps, with idle float auto-staking into Initia DEX LP. Demoed live across 4 ecosystems. DeFi track, built with a teammate. · [Project](https://dorahacks.io/buidl/43518)

---

## Connect

<p align="center">
  <a href="https://www.linkedin.com/in/diwakar-matsa-2a9733281">
    <img src="https://img.shields.io/badge/LinkedIn-Let's%20talk-FF6B35?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0D1117" alt="LinkedIn" />
  </a>
  <a href="mailto:void.00.diwakar@gmail.com">
    <img src="https://img.shields.io/badge/Email-Reach%20out-FF6B35?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0D1117" alt="Email" />
  </a>
  <a href="https://x.com/diwakr_matsa">
    <img src="https://img.shields.io/badge/X-Follow-FF6B35?style=for-the-badge&logo=x&logoColor=white&labelColor=0D1117" alt="X" />
  </a>
</p>

<p align="center"><sub><i>Correctness is a feature. Ship it like it's mainnet.</i></sub></p>
