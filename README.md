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
| | [**stockfront**](https://github.com/21r21a33333/stockfront) | Your AI prime broker for tokenized stocks — plain language in, a typed 11-primitive graph type-checked and emitted against live chain state, out |
| | [**amm-rs**](https://github.com/21r21a33333/amm-rs) | Wei-exact AMM quoting library — Uniswap, Curve, Aerodrome, and your own pools |
| | [**arb-router**](https://github.com/21r21a33333/arb-router) | On-chain arbitrage-detection router — venue-agnostic engine over a pool graph |
| **Wallet & chain infra** | [**walletkit**](https://github.com/21r21a33333/walletkit) | One safe Rust facade over alloy for EVM tx sending — swappable signers, un-bypassable policy, reorg-safe lifecycle |
| | [**btc-tee-escrow**](https://github.com/21r21a33333/btc-tee-escrow) | Trustless Bitcoin escrow inside a TEE — enclave-compatible server, Bitcoin Script validation, provably-fair dispute resolution |
| | [**blockchain**](https://github.com/21r21a33333/blockchain) | Uniform Go clients for interacting with many different chains |
| **Products & tooling** | [**ts-plugins-**](https://github.com/21r21a33333/ts-plugins-) | Contract-first, high-performance plugin infrastructure |
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

### 🏆 Solvent — a solver that holds no inventory · ETHOnline 2026

A **zero-inventory, protocol-agnostic intent resolver** on **1inch Aqua**. Solvent fills intent orders — starting with UniswapX — using non-custodial **maker** liquidity borrowed through Aqua *at the instant of settlement*, so it holds no capital of its own and keeps the spread.

- 💧 One maker balance backs solver inventory across many protocols at once, instead of each protocol needing its own siloed treasury
- 🔒 The maker's capital never leaves their control — Aqua records a virtual allowance, and real tokens move only at the pull
- ⚖️ Capped water-fill allocation across makers, with an off-chain reservation engine for the hard part: over-commitment between winning an auction and settling
- 🦀 Rust pipeline — ingest → price → reserve → fill → reconcile to the amount actually pulled

<p>
  <a href="https://ethglobal.com/showcase/the-solvent-84emi"><b>Showcase</b></a> ·
  <a href="https://github.com/thesolvent/solvent"><b>Code</b></a>
</p>

### 🏆 Stockfront — your AI prime broker for tokenized stocks · BNB Chain

A model writes a strategy in a second; running it takes minutes, several signatures, and a chain that moves in between. So the model is asked only for the part that doesn't expire — **the intent** — and a compiler does the rest.

- 🧩 Plain language, canvas blocks or JSON compile to **one typed graph** of 11 primitives — sources and actions, no protocol named anywhere in the grammar
- ✅ A type checker with 4 value types and 28 located diagnostics rejects a position fed to a step expecting tokens, an output spent twice, or a cycle
- ⛓️ Addresses, amounts and edges come from live chain state at emit time — not from the model — then every step is reviewed and user-signed
- 📉 Health factor before and after each borrow, named risk per strategy, and loops refused at the health floor rather than liquidated
- 🦀 Rust backend (hexagonal core → adapters → app), React frontend · built with a teammate

<p>
  <a href="https://www.youtube.com/watch?v=a685OVbK_sY"><b>Demo video</b></a> ·
  <a href="https://github.com/21r21a33333/stockfront"><b>Code</b></a>
</p>

**Also built**

- **[uniPay](https://github.com/TARS-Finance/uniPay)** · *Initia "Initiate" (DoraHacks)* — pay from any chain, settle and earn on Initia: customers pay in BTC, SOL or USDC on any major EVM, merchants receive USDC on Initia in ~30 seconds through trustless HTLC atomic swaps, with idle float auto-staking into Initia DEX LP. Demoed live across 4 ecosystems. DeFi track, built with a teammate. · [Project](https://dorahacks.io/buidl/43518)
