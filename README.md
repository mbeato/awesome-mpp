# Awesome MPP — The Machine Payments Protocol Registry [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![MPP Projects](https://img.shields.io/badge/projects-100%2B-brightgreen)](#contents)
[![MPP Services](https://img.shields.io/badge/services-80%2B-blue)](https://mpp.dev/services)
[![Payment Methods](https://img.shields.io/badge/chains-15%2B-purple)](#payment-methods)
[![SDKs](https://img.shields.io/badge/SDKs-TypeScript%20%7C%20Python%20%7C%20Rust%20%7C%20Go%20%7C%20Ruby%20%7C%20Elixir%20%7C%20.NET%20%7C%20Dart-orange)](#sdks)

> A curated list of resources, tools, SDKs, and services for the [Machine Payments Protocol (MPP)](https://mpp.dev) -- the open standard for AI agent payments and machine-to-machine commerce.

## What is MPP?

The **Machine Payments Protocol** is an open HTTP payment standard created by [Stripe](https://stripe.com) and [Tempo Labs](https://tempo.xyz), launched March 2026. It uses HTTP 402 (Payment Required) with an extensible challenge-credential-receipt flow so any client -- AI agents, apps, or humans -- can pay for any API or service in the same HTTP request.

- No API keys, billing accounts, or checkout flows required
- Payment-method agnostic: stablecoins, credit cards, Lightning, 15+ chains
- Supports one-time charges, sessions (pre-authorized spending), and streaming
- [IETF draft](https://datatracker.ietf.org/doc/draft-ryan-httpauth-payment/) (`draft-ryan-httpauth-payment`) co-authored by Stripe and Tempo

MPP is designed for the agentic web -- where AI agents autonomously discover, pay for, and consume API services without human intervention.

## Contents

- [Protocol & Specs](#protocol--specs)
- [SDKs](#sdks)
- [Payment Methods](#payment-methods)
- [Framework Integrations](#framework-integrations)
- [Infrastructure & Proxies](#infrastructure--proxies)
- [Agent Tools & CLIs](#agent-tools--clis)
- [Middleware & Extensions](#middleware--extensions)
- [Services](#services)
- [Community Projects](#community-projects)
- [Tempo Blockchain](#tempo-blockchain)
- [Resources](#resources)

## Protocol & Specs

- [mpp-specs](https://github.com/tempoxyz/mpp-specs) - Official MPP specification (RFC-style `Payment` HTTP auth scheme).
- [mpp](https://github.com/tempoxyz/mpp) - Protocol documentation site and service registry.
- [IETF Draft](https://datatracker.ietf.org/doc/draft-ryan-httpauth-payment/) - `draft-ryan-httpauth-payment` by Brendan Ryan (Tempo), Jeff Weinstein (Stripe).

## SDKs

### Official

- [mppx](https://github.com/wevm/mppx) - TypeScript SDK (server + client + proxy). Hono, Express, Next.js middleware. `npm i mppx` ![Stars](https://img.shields.io/github/stars/wevm/mppx)
- [pympp](https://github.com/tempoxyz/pympp) - Python SDK. `pip install pympp` ![Stars](https://img.shields.io/github/stars/tempoxyz/pympp)
- [mpp-rs](https://github.com/tempoxyz/mpp-rs) - Rust SDK. ![Stars](https://img.shields.io/github/stars/tempoxyz/mpp-rs)
- [tempo-go](https://github.com/tempoxyz/tempo-go) - Go SDK for Tempo blockchain with MPP client support. ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo-go)
- [tempo-ts](https://github.com/tempoxyz/tempo-ts) - TypeScript tooling for Tempo (used by mppx internally). ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo-ts)

### Community

- [mppx-rb](https://github.com/cjavdev/mppx-rb) - Ruby SDK.
- [mpp-go](https://github.com/deszhou/mpp-go) - Go SDK (community).
- [fastapi-mpp](https://github.com/SylvainCostes/fastapi-mpp) - FastAPI middleware for Python.
- [ZenHive/mpp](https://github.com/ZenHive/mpp) - Elixir implementation of MPP.
- [dotnet-sdk-mpp](https://github.com/evenuss/dotnet-sdk-mpp) - .NET SDK for MPP.
- [dart-tempo](https://github.com/Immadominion/dart-tempo) - Dart SDK for Tempo.

## Payment Methods

MPP is payment-method agnostic. Each chain/rail has its own plugin:

### Official (Tempo/Stripe)

- **Tempo** - TIP-20 stablecoins on Tempo L1. Built into `mppx`.
- **Stripe** - Credit/debit cards via Shared Payment Tokens. Built into `mppx`.
- [mpp-card](https://www.npmjs.com/package/mpp-card) - Fiat card payments.

### Solana

- [@solana/mpp](https://github.com/solana-foundation/mpp-sdk) - Official Solana Foundation SDK. ![Stars](https://img.shields.io/github/stars/solana-foundation/mpp-sdk)
- [@dexterai/mpp](https://github.com/Dexter-DAO/dexter-mpp) - Managed settlement (no blockchain infra needed).
- [mpp-solana](https://github.com/starc007/mpp-solana) - SPL token support.
- [mppx-solana](https://github.com/nitishxyz/mppx-solana) - mppx plugin for Solana.

### Lightning

- [@buildonspark/lightning-mpp-sdk](https://github.com/buildonspark/lightning-mpp-sdk) - Lightning via Spark. ![Stars](https://img.shields.io/github/stars/buildonspark/lightning-mpp-sdk)
- [@ambosstech/lightning-mpp-sdk](https://github.com/AmbossTech/lightning-mpp-sdk) - Lightning with LND + NWC adapters.
- [@axobot/mppx](https://github.com/zbdpay/axobot-mppx) - Lightning-native with pluggable adapters.

### Other Chains

- [@t2000/mpp-sui](https://github.com/mission69b/t2000) - Sui USDC payments. ![Stars](https://img.shields.io/github/stars/mission69b/t2000)
- [stellar-mpp-sdk](https://github.com/stellar-experimental/stellar-mpp-sdk) - Stellar.
- [xrpl-mpp-sdk](https://github.com/krkmu/xrpl-mpp-sdk) - XRP Ledger.
- [mpp-abstract](https://github.com/Abstract-Foundation/mpp-abstract) - Abstract (custom intents + escrow).
- [mpp-movement](https://github.com/MoveIndustries/mpp-movement) - Movement Network.
- [mpp-ton](https://github.com/TesseraeVentures/mpp-ton) - TON.
- [algorand-mpp-sdk](https://github.com/GoPlausible/algorand-mpp-sdk) - Algorand.
- [mpp-avalanche](https://github.com/ashucoder9/mpp-avalanche) - Avalanche (streaming payment channels).
- [mppx-multiversx](https://github.com/sasurobert/mppx-multiversx) - MultiversX.
- [mega-mpp-sdk](https://github.com/ifavo/mega-mpp-sdk) - MegaETH.
- [skalenetwork/mpp-sdk](https://github.com/skalenetwork/mpp-sdk) - SKALE.
- [zimppy](https://github.com/betterclever/zimppy) - Zcash (private payments for AI agents). ![Stars](https://img.shields.io/github/stars/betterclever/zimppy)
- [@0xsquid/mpp](https://www.npmjs.com/package/@0xsquid/mpp) - Cross-chain via Squid Router.
- [mppx-stableyard](https://github.com/stableyardfi/mppx-stableyard) - Any chain in, any chain out, fiat settlement.
- [@monad-crypto/mpp](https://github.com/monad-crypto/mpp) - Monad.
- [@caypo/mpp-canton](https://www.npmjs.com/package/@caypo/mpp-canton) - Canton Network (USDCx).
- [xrpl-mpp-stack](https://github.com/lgcarrier/xrpl-mpp-stack) - XRP Ledger (Python, charge + session).
- [@raycashxyz/mpp](https://www.npmjs.com/package/@raycashxyz/mpp) - Private payments via Raycash.

## Framework Integrations

Built into `mppx`:
- **Hono** - `import { Mppx } from 'mppx/hono'`
- **Express** - `import { Mppx } from 'mppx/express'`
- **Next.js** - `import { Mppx } from 'mppx/next'`
- **Elysia** - `import { Mppx } from 'mppx/elysia'`
- **Bun.serve** / **Deno.serve** - Framework-agnostic `mppx/server`

Community:
- [fastapi-mpp](https://github.com/SylvainCostes/fastapi-mpp) - FastAPI (Python).
- [@agentcash/router](https://www.npmjs.com/package/@agentcash/router) - Next.js App Router with MPP + x402 + API key auth.
- [mpp-aws](https://github.com/i-norden/mpp-aws) - AWS infrastructure integration.

## Infrastructure & Proxies

- [mppx proxy](https://github.com/wevm/mppx) - Built into mppx. Wrap any API with MPP payment gating (zero code changes).
- [mppx-proxy](https://github.com/starc007/mppx-proxy) - Standalone reverse proxy for MPP.
- [mpp-proxy-cf](https://github.com/tempoxyz/mpp-proxy-cf) - Cloudflare Workers MPP proxy (official).
- [openvps](https://github.com/kartojal/openvps) - MPP-powered VPS hosting -- AI agents pay for compute. ![Stars](https://img.shields.io/github/stars/kartojal/openvps)
- [github-mpp-proxy](https://github.com/aLjTap/github-mpp-proxy) - GitHub REST API proxy with MPP payments.
- [mppscan.com](https://mppscan.com) - Transaction explorer and service discovery.
- [mpp-cloudflare-dynamic-edge-agent](https://github.com/sam00101011/mpp-cloudflare-dynamic-edge-agent) - Dynamic edge agent on Cloudflare Workers.
- [tollbooth](https://github.com/abhay/tollbooth) - Solana payment gateway with MPP, gasless fee relayer, axum middleware.

## Agent Tools & CLIs

- [incur](https://github.com/wevm/incur) - CLI framework for agents and humans (by wevm). ![Stars](https://img.shields.io/github/stars/wevm/incur)
- [incur-rs](https://github.com/tempoxyz/incur-rs) - Rust port of incur.
- [agent-skills](https://github.com/tempoxyz/agent-skills) - Official Tempo agent skill pack (`npx skills add tempoxyz/agent-skills`).
- [wallet](https://github.com/tempoxyz/wallet) - CLI wallet + HTTP client with built-in MPP support. ![Stars](https://img.shields.io/github/stars/tempoxyz/wallet)
- [@kakedashi/paylog](https://www.npmjs.com/package/@kakedashi/paylog) - CLI to view MPP spending history.
- [@heyamiko/amiko-cli](https://www.npmjs.com/package/@heyamiko/amiko-cli) - CLI for Amiko AI Agent Marketplace.
- [human402](https://github.com/joohhnnn/human402) - Human-facing 402 payment page for MPP.
- [MPP-Inspector](https://github.com/amgb20/MPP-Inspector) - CLI + web dashboard for debugging MPP flows. "Postman for MPP."
- [mcp-protocol-tester](https://github.com/whiteknightonhorse/mcp-protocol-tester) - Universal test suite for MCP servers with dual-rail payment testing (x402 + MPP).
- [openprice](https://github.com/tldr-wknd/openprice) - Price discovery middleware for the agent economy.

## Middleware & Extensions

- [mppx-rate-limit](https://github.com/leigents/mppx-rate-limit) - Rate limiting for MPP routes.
- [mppx-token-gate](https://github.com/douglasborthwick-crypto/mppx-token-gate) - Token-gate routes via signed wallet attestations (32 chains).
- [agenttax-mppx](https://github.com/AgentTax/agenttax-mppx) - Tax middleware (sales tax + capital gains) for AI agent transactions.
- [mpp-integration](https://github.com/observer-protocol/mpp-integration) - Trust/reputation layer for MPP sellers.
- [sardis-guard-mpp](https://github.com/EfeDurmaz16/sardis-guard-mpp) - Financial intelligence for AI agent payments.
- [costillery](https://github.com/wytcab/costillery) - Receipt intelligence for AI agents. Auto-captures MPP and x402 receipts.
- [agentlair-mpp-identity-bridge](https://github.com/piiiico/agentlair-mpp-identity-bridge) - Verifiable agent identity via DIDs and Ed25519 attestations.
- [@clearagent/mpp](https://www.npmjs.com/package/@clearagent/mpp) - KYA (Know Your Agent) compliance screening for MPP.
- [agent-verifier](https://github.com/goodmeta/agent-verifier) - Agent spending verification with budget caps and cross-agent tracking.
- [secure-exec](https://github.com/achilliesbot/secure-exec) - Sandboxed tool execution oracle with IAM-gated dry-run. x402/MPP payment gate.

## Services

### First-Party (native MPP)

Services with built-in MPP payment support:

- **AgentMail** - Email for AI agents.
- **Allium** - Blockchain data.
- **Browserbase** - Headless browser API.
- **Dune** - Crypto analytics.
- **Parallel** - Agent-to-agent coordination.
- [APIMesh](https://github.com/mbeato/conway) - 22 pay-per-call web analysis APIs (security audits, tech stack, email verify, SEO). Supports x402 + MPP.
- [paid-image-api](https://github.com/cepuyut/paid-image-api) - Pay-per-request AI image generation on Tempo.
- [Dtelecom](https://github.com/dteIecom/Dtelecom) - Real-time voice, video & voice AI. Pay-per-use via x402/MPP.

### Proxied (via mpp.tempo.xyz)

Available through Tempo's MPP proxy -- pay with any MPP method:

**AI/ML:** Anthropic, OpenAI, Google Gemini, Mistral AI, Groq, DeepSeek, Perplexity, OpenRouter, Replicate, fal.ai, Modal, Stability AI, Suno

**Data & Search:** Exa, Firecrawl, Tavily, Brave Search, Wolfram|Alpha, SerpAPI, DiffBot, EDGAR, CoinGecko, Alpha Vantage

**Developer Tools:** Judge0, Deepgram, DeepL, Mapbox, Mathpix, IPinfo, Hunter, ScreenshotOne, BuiltWith

**Business:** Apollo, Billboard, RentCast, SpyFu, OxyLabs, 2Captcha

**Travel & Misc:** AviationStack, FlightAPI, GoFlightLabs, OpenWeather, PostalForm, KicksDB, Abstract APIs (12+ services)

## Community Projects

### Agent Frameworks

- [tempo-mpp-agent-starter](https://github.com/efidal/tempo-mpp-agent-starter) - Mainnet-first MPP automation starter. ![Stars](https://img.shields.io/github/stars/efidal/tempo-mpp-agent-starter)
- [Ottie](https://github.com/jiayaoqijia/Ottie) - Self-evolving agent for Ethereum/crypto. ![Stars](https://img.shields.io/github/stars/jiayaoqijia/Ottie)
- [mpp-agentkit](https://github.com/0xOsiris/mpp-agentkit) - World Agent Kit Library for MPP.
- [spire](https://github.com/suverenum/spire) - Home for AI agent wallets. ![Stars](https://img.shields.io/github/stars/suverenum/spire)
- [Caypo](https://github.com/anilkaracay/Caypo) - Agent finance on institutional rails (MPP + USDCx + MCP).
- [OpenAgentPay](https://github.com/alokemajumder/OpenAgentPay) - Open-source payment orchestration. 17 packages, 14 routing strategies, 8 payment connectors.
- [helix](https://github.com/adrianhihi/helix) - Self-healing infrastructure for AI agent payments. 90% auto-recovery.
- [helix-tempo](https://github.com/adrianhihi/helix-tempo) - Self-healing payment SDK for agents on Tempo.
- [agentmart](https://github.com/teckedd-code2save/agentmart) - Autonomous agent-to-agent economy. Agents hire agents.
- [clawdmarket](https://github.com/trillskillz/clawdmarket) - Agent-to-agent marketplace. No humans required.
- [Masumi-MPP-Bridge](https://github.com/Sarthib7/Masumi-MPP-Bridge) - Universal payment gateway for MPP-enabled agents on Masumi Network.
- [universal-pay](https://github.com/Bobbaybuilding/universal-pay) - Universal 402 payment skill via Across crosschain bridging.

### MCP Bridges

- [mpp-mcp](https://github.com/leigents/mpp-mcp) - Turn MCP server tools into paid endpoints via MPP.
- [mpp-bundler](https://github.com/vikram14s/mpp-bundler) - Claude Code plugin to scaffold MPP billing into any API.
- [shopgraph](https://github.com/laundromatic/shopgraph) - Product data enrichment MCP server (Stripe MPP).
- [tempo-mcp](https://github.com/arome3/tempo-mcp) - MCP server for autonomous stablecoin payments on Tempo.
- [mcp-pay](https://github.com/neul-labs/mcp-pay) - Payment awareness layer for MCP.
- [delx-protocol](https://github.com/davidmosiah/delx-protocol) - Open-core MCP, A2A, REST, x402, and MPP-compatible protocol surfaces.

### Applications

- [zk-proof-service](https://github.com/Himess/zk-proof-service) - ZK proof generation (pay per Groth16 proof via MPP).
- [privagent-service](https://github.com/Himess/privagent-service) - Privacy-preserving payment proofs via Tempo.
- [content-for-machines](https://github.com/xlxqxs/content-for-machines) - Pay-per-access content gating for AI agents.
- [video-gen-mpp](https://github.com/lucas-walsh/video-gen-mpp) - Video generation with MPP payments.
- [onlygate-tempo-mpp-wrapper](https://github.com/Kenny50/onlygate-tempo-mpp-wrapper) - Zero-trust HITL wrapper for MPP spending controls.
- [trenchcoat-mpp](https://github.com/Keeeeeeeks/trenchcoat-mpp) - Tell your agent to order you UberEats, using MPP.
- [mpp-uniswap-agent](https://github.com/eek-uniswap/mpp-uniswap-agent) - Autonomous agent: ETH → Uniswap → USDC → MPP → LLM inference. No API keys.
- [remlo](https://github.com/winsznx/remlo) - Borderless enterprise payroll on Tempo L1.
- [presto](https://github.com/mmashiat/presto) - Storefront layer for MPP-compatible agent services.
- [TheMinutes](https://github.com/xfajarr/TheMinutes) - Service router for AI agents on Tempo. Discover, compare, route to 100+ MPP services.
- [tempo-private-payments](https://github.com/zhivkoto/tempo-private-payments) - Confidential stablecoin transfers via stealth addresses + MPP.

### Demos & Examples

- [stellar-mpp-demo](https://github.com/stellar-experimental/stellar-mpp-demo) - Stellar chat via micropayments.
- [mpp-card-charge-demo](https://github.com/armsteadj1/mpp-card-charge-demo) - Interactive card charge flow.
- [MPP_Visa-TAP_PoC](https://github.com/freedomfighter-007/MPP_Visa-TAP_PoC) - MPP + Visa TAP proof of concept.
- [example-mega-mpp-cf](https://github.com/ifavo/example-mega-mpp-cf) - MegaETH MPP on Cloudflare Workers.
- [mpp-one-payment](https://github.com/delineas/mpp-one-payment) - TypeScript single payment example.
- [tempo-demos](https://github.com/kwattana/tempo-demos) - AI agents making autonomous payments — DoorDash, Shopify, GPU Marketplace demos.
- [OPK-MPP-Tempo-Hackathon](https://github.com/zhangzhongnan928/OPK-MPP-Tempo-Hackathon) - OPK Pay Terminal + MPP. One rail for human and machine commerce.
- [tempo-x402-demo](https://github.com/compusophy/tempo-x402-demo) - Interactive x402 demo on Tempo.
- [emv-tempo](https://github.com/zhangzhongnan928/emv-tempo) - EMV contactless card payments settled on Tempo.

## Tempo Blockchain

The payments infrastructure powering MPP:

- [tempo](https://github.com/tempoxyz/tempo) - The Tempo blockchain. ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo)
- [tempo-apps](https://github.com/tempoxyz/tempo-apps) - Frontend apps monorepo. ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo-apps)
- [tempo-foundry](https://github.com/tempoxyz/tempo-foundry) - Foundry fork with Tempo support. ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo-foundry)
- [tempo-std](https://github.com/tempoxyz/tempo-std) - Solidity contracts/libraries. ![Stars](https://img.shields.io/github/stars/tempoxyz/tempo-std)
- [ledger-app-tempo](https://github.com/tempoxyz/ledger-app-tempo) - Ledger hardware wallet plugin.
- [docs](https://github.com/tempoxyz/docs) - Ecosystem documentation.

## Resources

### Documentation

- [mpp.dev](https://mpp.dev) - Protocol documentation and service directory.
- [docs.tempo.xyz](https://docs.tempo.xyz) - Tempo + MPP developer docs.
- [stripe.com/blog/machine-payments-protocol](https://stripe.com/blog/machine-payments-protocol) - Stripe's MPP launch announcement.

### Articles

- [The Machine Payments Protocol](https://tempo.xyz/blog/mainnet/) - Tempo mainnet launch + MPP introduction.
- [Stripe Agentic Commerce Solutions](https://stripe.com/blog/introducing-our-agentic-commerce-solutions) - Stripe's broader agent payment strategy.

## Keywords

Searching for MPP tools? This list covers: **MPP registry**, **MPP directory**, **MPP tools list**, **Machine Payments Protocol tools**, **Stripe MPP SDK**, **Tempo payments SDK**, **AI agent payments**, **HTTP 402 payment protocol**, **agent-to-agent payments**, **machine-to-machine payments**, **agentic commerce tools**, **pay-per-call API**, **micropayment protocol**, **stablecoin payments for agents**, **MCP payment tools**, **paid API directory**.

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
