<!--
  Diwakar Matsa — GitHub profile README
  Theme: sleek minimal dark · accent #FF6B35 (ember) · bg #0D1117
  Banner is a hand-built animated SVG (assets/banner.svg), not a template.
-->

<p align="center">
  <img src="./assets/banner.svg" alt="Diwakar Matsa — Blockchain & Backend Engineer" width="100%" />
</p>

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
  <img src="https://komarev.com/ghpvc/?username=21r21a33333&label=Profile%20views&color=FF6B35&style=flat" alt="Profile views" />
</p>

<p align="center">
  <a href="https://github.com/21r21a33333">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=2800&pause=800&color=FF6B35&center=true&vCenter=true&width=820&height=48&lines=Blockchain+%26+Backend+Engineer;Rust-first+%C2%B7+Bitcoin+%C2%B7+EVM+%C2%B7+multi-chain;Relayers%2C+indexers+%26+secure+signing+infra;AWS+%C2%B7+mainnet-grade%2C+security-critical+systems" alt="Typing intro" />
  </a>
</p>

---

## About

I'm Diwakar — a **Blockchain & Backend Engineer** writing production **Rust** for Bitcoin, EVM, and multi-chain systems where correctness and security aren't optional.

I work across the cross-chain stack — **relayers, indexers, watchers / executors, and secure signing infrastructure**.

- 🦀 Rust-first, with Go, C++, TypeScript & Solidity in the toolbox
- ⛓️ HTLCs, Bitcoin Script & multisig cosigners — across Bitcoin, EVM, Solana, Dogecoin, Litecoin & Zcash
- ☁️ AWS, Docker, CI/CD
- 📍 Hyderabad, India

---

## What I'm building now

**Crypto SDE 1 @ [Garden Finance](https://garden.finance) — a Bitcoin R&D studio.**

I build production Rust across Garden's cross-chain stack — **relayers, indexers, and secure signing infrastructure** powering **trust-minimized settlement** over Bitcoin, EVM, and many other chains.

> Specifics are under NDA — the open-source work below is the same caliber.

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

---

## Tech

<p align="center">
  <img src="https://skillicons.dev/icons?i=rust,go,cpp,c,java,solidity,ts,py,nodejs,react,nextjs,postgres,mongodb,firebase,docker,aws,githubactions,linux&theme=dark&perline=9" alt="Tech stack" />
</p>

---

## Featured open-source

| Project | What it is | Stack |
| --- | --- | --- |
| [**walletkit**](https://github.com/21r21a33333/walletkit) | Rust wallet-infrastructure library — one safe facade over alloy for EVM tx sending: swappable signer backends (keys never leave), un-bypassable policy, reorg-safe lifecycle; 4337 / 7702 / paymasters plug in | Rust · alloy |
| [**amm-rs**](https://github.com/21r21a33333/amm-rs) | Open, wei-exact AMM quoting library — Uniswap, Curve, Aerodrome, and your own pools | Rust |
| [**arb-router**](https://github.com/21r21a33333/arb-router) | On-chain arbitrage-detection router — venue-agnostic engine over a pool graph | Rust |
| [**blockchain**](https://github.com/21r21a33333/blockchain) | Uniform clients for interacting with many different blockchains | Go |
| [**btc-tee-escrow**](https://github.com/21r21a33333/btc-tee-escrow) | Trustless Bitcoin escrow inside a Trusted Execution Environment — TEE-compatible server, Bitcoin Script validation, provably-fair dispute resolution | Rust · Bitcoin |
| [**ts-plugins-**](https://github.com/21r21a33333/ts-plugins-) | Contract-first, high-performance plugin infrastructure | TypeScript |
| [**yt-notes**](https://github.com/21r21a33333/yt-notes) | Local pipeline turning any YouTube video into a structured note with frames, diagrams & timestamp links | Python |

**More** — [MuadibRouter](https://github.com/21r21a33333/MuadibRouter) · EVM routing & execution engine • [openfhe-secure-maxcosine](https://github.com/21r21a33333/openfhe-secure-maxcosine) · FHE encrypted-vector search • [choose-rich](https://github.com/21r21a33333/choose-rich) · multi-chain gaming API • [distributed-systems](https://github.com/21r21a33333/distributed-systems)

---

## Recent hackathon

### 🏆 uniPay — pay from any chain, settle & earn on Initia

A multi-chain merchant checkout: customers pay in **BTC, SOL, or USDC on any major EVM**, and merchants receive **USDC on Initia in ~30 seconds** through **trustless HTLC atomic swaps** — no bridges, no custodians. Idle merchant float can auto-stake into Initia DEX LP positions that earn swap fees *and* staking rewards at once via Enshrined Liquidity.

- ⚡ Sub-30-second settlement, demoed live across **4 ecosystems** — Bitcoin, Solana, EVM, Initia
- 🔗 HTLCs on Bitcoin / EVM / Solana / Initia + a custom Initia EVM rollup, per-chain watcher & executor services, and an orderbook / solver / staking backend
- 🧩 React + InterwovenKit frontend over the Initia Interwoven Bridge
- 🏅 DeFi track · built with a teammate

<p>
  <a href="https://dorahacks.io/buidl/43518"><b>Project</b></a> ·
  <a href="https://github.com/TARS-Finance/uniPay"><b>Code</b></a>
</p>

---

## Connect

<p align="center">
  <a href="https://www.linkedin.com/in/diwakar-matsa-2a9733281">
    <img src="https://img.shields.io/badge/LinkedIn-Let's%20talk-FF6B35?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0D1117" alt="LinkedIn" />
  </a>
  <a href="mailto:void.00.diwakar@gmail.com">
    <img src="https://img.shields.io/badge/Email-Reach%20out-FF6B35?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0D1117" alt="Email" />
  </a>
</p>

<p align="center"><sub><i>Correctness is a feature. Ship it like it's mainnet.</i></sub></p>
