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
- [mpp-spl](https://github.com/nullxnothing/mpp-spl) - SPL token + pump.fun payment layer. Token registry, Jupiter/bonding curve pricing, charge config resolver. ![Stars](https://img.shields.io/github/stars/nullxnothing/mpp-spl)

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

- [Alchemy](https://www.mpppay.fun/ecosystem) - Blockchain data APIs including Core RPC APIs, Prices API, Portfolio API, and NFT API across 100+ chains.
- [Allium](https://www.mpppay.fun/ecosystem) - System of record for onchain finance. Real-time blockchain data: token prices, wallet balances, transactions, PnL, and SQL explorer.
- [Codex](https://www.mpppay.fun/ecosystem) - Comprehensive onchain data API for tokens and prediction markets. Real-time prices, charts, trades, and wallet analytics across 80+ networks via GraphQL.
- [QuickNode](https://www.mpppay.fun/ecosystem) - Quicknode Core Node API for 80+ blockchains and 140+ networks.
- [Tempo RPC](https://www.mpppay.fun/ecosystem) - Tempo blockchain JSON-RPC access (mainnet and testnet).
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

- [Object Storage](https://www.mpppay.fun/ecosystem) - S3/R2-compatible object storage with dynamic per-size pricing.
- [StableUpload](https://www.mpppay.fun/ecosystem) - Pay-per-upload file hosting and static site hosting with custom domains — 6 month TTL.
- [Code Storage](https://code.storage) - Paid Git repository creation — create repos and get authenticated clone URLs.
- [Judge0](https://judge0.com) - Online code execution — run source code in 60+ programming languages with sandboxed isolation.
- [Modal](https://modal.com) - Serverless GPU compute for sandboxed code execution and AI/ML workloads.
- [ScreenshotOne](https://screenshotone.com) - Website screenshot API — capture any URL, HTML, or markdown as PNG, JPEG, WebP, or PDF. Full-page, element selection, dark mode, ad blocking, and more.
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
- [x402-proxy](https://github.com/cascade-protocol/x402-proxy) - `curl` for x402 and MPP paid APIs. Auto-pays HTTP 402 responses on Base, Solana, and Tempo. MCP stdio proxy for AI agents, wallet management, pay-per-token streaming via MPP sessions. `npx x402-proxy`. ([npm](https://www.npmjs.com/package/x402-proxy))

- [Parallel](https://www.mpppay.fun/ecosystem) - Web search, page extraction, and multi-hop web research.
- [Brave Search](https://brave.com/search) - Independent web search — web, news, images, videos, AI answers, and LLM context. Privacy-first search from a large independent index.
- [Exa](https://exa.ai) - AI-powered web search, content retrieval, and answers.
- [SerpApi](https://serpapi.com) - Google Flights search — real-time prices, schedules, and booking options.
- [Tavily](https://tavily.com) - AI-optimized web search, content extraction, site mapping, and crawling API.
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

- [mpay](https://www.npmjs.com/package/mpay) - TypeScript SDK for the [**Machine Payments Protocol**](https://machinepayments.dev).
- [mppfinance](git+https://github.com/mppfinance/mppfinance-sdk.git) - Virtual Visa cards for AI agents — powered by Machine Payments Protocol.
- [@stellar/mpp](git+https://github.com/stellar/stellar-mpp-sdk.git) - Stellar blockchain payment method for the Machine Payments Protocol (MPP).
- [@atxp/mpp](git+https://github.com/atxp-dev/sdk.git) - ATXP MPP (Machine Payments Protocol) support.
- [@moldy/mega-mpp-sdk](git+https://github.com/ifavo/mega-mpp-sdk.git) - MegaETH payment method for the Machine Payments Protocol.
- [@raycashxyz/mpp-pay](git+https://github.com/raycashxyz/mpp-pay.git) - CLI for making paid API requests via the Machine Payments Protocol.
- [@grantex/mpp](git+https://github.com/mishrasanjeev/grantex.git) - Grantex agent identity and delegation for MPP (Machine Payments Protocol).
- [@paytoll/sdk](git+https://github.com/paytoll/sdk.git) - Developer toolkit for accepting machine payments on Solana via the Machine Payments Protocol (MPP).
- [clawmpp](https://www.npmjs.com/package/clawmpp) - Machine Payments Protocol integration for OpenClaw — one wallet, every AI service.
- [@solobank/mpp-solana](https://www.npmjs.com/package/@solobank/mpp-solana) - Solana USDC payment method for the Machine Payments Protocol (MPP).
- [x402](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [@x402/evm](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol EVM Implementation.
- [@x402/extensions](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol Extensions.
- [@x402/svm](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol SVM Implementation.
- [@x402/core](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [@x402/fetch](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol Fetch Extension.
- [@coinbase/x402](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [x402-fetch](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [twitsh](git+https://github.com/etherlect/twitsh.git) - X/Twitter data CLI with x402 micropayment handling.
- [@b3dotfun/anyspend-x402](git+https://github.com/b3-fun/anyspend-x402.git) - AnySpend x402 Payment Protocol - Extended implementation with multi-chain support.
- [x402-axios](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [@relai-fi/x402](git+https://github.com/web3luka/relai-sdk.git) - Unified x402 payment SDK for Solana, Base, Avalanche, SKALE Base, SKALE BITE, Polygon, and Ethereum. Automatic 402 handling with zero gas fees.
- [@x402/express](git+https://github.com/coinbase/x402.git) - x402 Payment Protocol.
- [x402-stacks](git+https://github.com/tony1908/x402Stacks.git) - TypeScript library for implementing x402 payment protocol on Stacks blockchain.
- [@b3dotfun/anyspend-x402-fetch](git+https://github.com/b3-fun/anyspend-x402.git) - AnySpend x402 Fetch client - Extended x402 payment protocol integration for native fetch API with multi-token support.
## Services

### First-Party (native MPP)

Services with built-in MPP payment support:

- **AgentMail** - Email for AI agents.
- **Allium** - Blockchain data.
- **Browserbase** - Headless browser API.
- **Dune** - Crypto analytics.
- **Parallel** - Agent-to-agent coordination.
- [APIMesh](https://github.com/mbeato/conway) - 27 pay-per-call APIs for AI agents (web-checker, http-status-checker, favicon-checker, seo-audit, email-verify, tech-stack, +21 more). Supports x402 + MPP.
- [paid-image-api](https://github.com/cepuyut/paid-image-api) - Pay-per-request AI image generation on Tempo.
- [Dtelecom](https://github.com/dteIecom/Dtelecom) - Real-time voice, video & voice AI. Pay-per-use via x402/MPP.
- [Surf](https://surf.cascade.fyi) - Pay-per-use Twitter, Reddit, web, and inference APIs for AI agents. Dual-protocol (x402 + MPP) on Base, Solana, and Tempo. Unified MCP server at `/mcp`. ([GitHub](https://github.com/cascade-protocol/surf))

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

- [StableTravel](https://www.mpppay.fun/ecosystem) - Pay-per-request travel APIs — flights, hotels, activities, transfers, and real-time flight tracking. Powered by Amadeus and FlightAware.
- [Stripe Climate](https://www.mpppay.fun/ecosystem) - Fund permanent carbon removal projects via Stripe Climate.
- [Browserbase](https://www.mpppay.fun/ecosystem) - Headless browser sessions, web search, and page fetching for AI agents.
- [AgentMail](https://www.mpppay.fun/ecosystem) - Email inboxes for AI agents.
- [Dune](https://www.mpppay.fun/ecosystem) - Query across raw transaction data, decoded smart contract events, stablecoin flows, RWA tracking, protocol analytics, DeFi positions, NFT activity, blockchain market research, and whatever is trending.
- [PostalForm](https://www.mpppay.fun/ecosystem) - Print and mail real letters and documents via AI agents.
- [Prospect Butcher](https://www.mpppay.fun/ecosystem) - Order sandwiches for pickup in Brooklyn — the first food purchase made entirely by an AI agent.
- [StableEmail](https://www.mpppay.fun/ecosystem) - Pay-per-send email delivery, forwarding inboxes, and custom subdomains — no API keys or accounts.
- [StableEnrich](https://www.mpppay.fun/ecosystem) - Pay-per-request research APIs — people, companies, web search, scraping, places, social media, and contact enrichment.
- [StablePhone](https://www.mpppay.fun/ecosystem) - AI phone calls, dedicated phone numbers, and iMessage/FaceTime lookup — pay per request.
- [StableSocial](https://www.mpppay.fun/ecosystem) - Pay-per-request social media data from TikTok, Instagram, Facebook, and Reddit.
- [StableStudio](https://www.mpppay.fun/ecosystem) - Pay-per-generation AI image and video creation — Nano Banana, GPT Image, Grok, Flux, Sora, Veo, Seedance, and Wan.
- [OpenAI](https://openai.com) - Chat completions, embeddings, image generation, and audio with model-tier pricing.
- [Anthropic](https://anthropic.com) - Claude chat completions (Sonnet, Opus, Haiku) via native and OpenAI-compatible APIs.
- [OpenRouter](https://openrouter.ai) - Unified API for 100+ LLMs with live per-model pricing.
- [2Captcha](https://2captcha.com) - CAPTCHA solving API — reCAPTCHA, Turnstile, hCaptcha, image captchas, and more.
- [Alpha Vantage](https://www.alphavantage.co) - Financial market data — stock prices, forex, crypto, commodities, economic indicators, technical analysis, and news sentiment.
- [Apollo](https://www.apollo.io) - People and company enrichment, lead search, and sales intelligence with 275M+ contacts.
- [AviationStack](https://aviationstack.com) - Real-time and historical flight tracking, airports, airlines, and schedules.
- [Billboard](https://x.com/MPPBillboard) - Post to @MPPBillboard on X. Price starts at $0.01 and doubles with every post. The ultimate AI agent billboard.
- [BuiltWith](https://builtwith.com) - Technology profiling for websites — detect tech stacks, find sites using specific technologies, discover domain relationships, trends, and competitive intelligence across 100M+ websites.
- [Clado](https://clado.ai) - People search, LinkedIn enrichment, and deep research for lead generation.
- [CoinGecko](https://www.coingecko.com) - Cryptocurrency market data — prices, charts, market cap, exchanges, trending coins, global stats, NFTs, derivatives, and on-chain data.
- [Company Enrichment](https://www.abstractapi.com/api/company-enrichment) - Enrich company data from a domain name.
- [Deepgram](https://deepgram.com) - Industry-leading speech AI — transcribe audio from URLs with Nova-3, generate natural speech with Aura-2 TTS, and analyze text for sentiment, topics, intents, and summaries.
- [DeepL](https://www.deepl.com) - Professional translation and text improvement — translate text between 30+ languages with industry-leading quality, or improve and rephrase text with DeepL Write.
- [DeepSeek](https://deepseek.com) - Frontier AI models — DeepSeek-V3 for fast chat and code, DeepSeek-R1 for deep chain-of-thought reasoning. OpenAI-compatible API format. Among the most capable and cost-efficient models available.
- [Diffbot](https://www.diffbot.com) - Web data extraction — articles, products, discussions, images, videos, and auto-detect.
- [Diffbot KG](https://www.diffbot.com) - Knowledge Graph — search 10B+ entities and enrich company/person records.
- [Diffbot NL](https://www.diffbot.com) - Natural language processing — NER, sentiment, facts, summarization.
- [EDGAR (SEC)](https://www.sec.gov/developer) - SEC EDGAR public financial data — company filing history, XBRL financial facts (income statements, balance sheets, cash flows), and full-text search across all public filings. No API key required.
- [EDGAR Full-Text Search](https://efts.sec.gov) - Full-text search across all SEC filings — 10-Ks, 10-Qs, 8-Ks, proxy statements, and more. Search by keyword, company name, form type, and date range.
- [Email Reputation](https://www.abstractapi.com/api/email-reputation-api) - Check the reputation and risk score of an email address.
- [Exchange Rates](https://www.abstractapi.com/api/exchange-rate-api) - Live, historical, and conversion exchange rates for 150+ currencies.
- [fal.ai](https://fal.ai) - Image, video, and audio generation with 600+ models (Flux, SD, Recraft, Grok).
- [Firecrawl](https://firecrawl.dev) - Web scraping, crawling, and structured data extraction for LLMs.
- [FlightAPI](https://flightapi.io) - Real-time flight prices, tracking, and airport schedules from 700+ airlines.
- [GoFlightLabs](https://goflightlabs.com) - Real-time flight tracking, prices, schedules, and airline data.
- [Google Gemini](https://ai.google.dev) - Gemini text generation, Veo video, and Nano Banana image generation with model-tier pricing.
- [Google Maps](https://developers.google.com/maps) - Google Maps Platform — geocoding, directions, places, routes, tiles, weather, air quality, and more.
- [Grok](https://x.ai) - xAI models — chat, web/X search, code execution, image generation/editing, and text-to-speech.
- [Groq](https://groq.com) - Ultra-fast LLM inference — Llama 3.3, DeepSeek R1, Gemma 2, GPT-OSS, Qwen, Whisper, and PlayAI TTS. OpenAI-compatible API with industry-leading speed.
- [Holidays](https://www.abstractapi.com/api/holidays-api) - Public holiday data for 200+ countries.
- [Hunter](https://hunter.io) - Email finding, verification, and company enrichment for outreach and lead generation.
- [IBAN Validation](https://www.abstractapi.com/api/iban-validation-api) - Validate International Bank Account Numbers (IBANs).
- [IP Intelligence](https://www.abstractapi.com/api/ip-intelligence-api) - Detect VPNs, proxies, bots, and Tor nodes by IP address.
- [IPinfo](https://ipinfo.io) - IP intelligence — geolocation, ASN, privacy detection, carrier data, and hosting identification.
- [KicksDB](https://kicks.dev) - Sneaker & streetwear market data — prices, sales history, and availability from StockX, GOAT, and more.
- [Mapbox](https://www.mapbox.com) - Location and mapping APIs — geocoding, directions, isochrones, matrix routing, map matching, static maps, and spatial queries.
- [Mathpix](https://mathpix.com) - OCR for math, science, and documents — extract LaTeX, MathML, and Mathpix Markdown from images and handwriting.
- [Mistral AI](https://mistral.ai) - Premier and open-source LLMs — Mistral Large, Medium, Small, Codestral, Magistral reasoning, Pixtral vision, text embeddings, and content moderation.
- [OpenWeather](https://openweathermap.org) - Global weather data — current conditions, 5-day forecasts, hourly forecasts, air quality index with pollutants, geocoding, and One Call 3.0 with full weather suite and government alerts.
- [Oxylabs](https://oxylabs.io) - Web scraping API with geo-targeting by country, state, and city. Fetch any public URL with JavaScript rendering support.
- [Perplexity](https://perplexity.ai) - AI-powered search — Sonar chat with real-time web grounding, web search, and embeddings.
- [Phone Intelligence](https://www.abstractapi.com/api/phone-validation-api) - Validate and get carrier info for phone numbers worldwide.
- [RentCast](https://rentcast.io) - US real estate intelligence — property records, AVM valuations, rent estimates, sale/rental listings, and market statistics.
- [Replicate](https://replicate.com) - Run thousands of open-source AI models via API — image generation, language models, speech recognition, video, and more. Pay only for what you use.
- [SpyFu](https://spyfu.com) - Competitor keyword research — SEO rankings, PPC ads, ad history, and domain analytics. 18+ years of historical data.
- [Stability AI](https://stability.ai) - Generative AI platform for images, 3D models, and audio — text-to-image, editing, upscaling, and more.
- [Suno](https://sunoapi.org) - AI music generation — create full songs, generate lyrics, and build custom music tracks with state-of-the-art AI models. Supports custom styles, vocals, and instrumental modes.
- [Timezone](https://www.abstractapi.com/api/time-date-timezone-api) - Current time and timezone conversion for any location.
- [VAT](https://www.abstractapi.com/api/vat-validation-rates-api) - VAT number validation, rate calculation, and category lookup for EU.
- [Web Scraping](https://www.abstractapi.com/api/web-scraping-api) - Scrape web pages with optional JavaScript rendering.
- [Wolfram|Alpha](https://www.wolframalpha.com) - Computational knowledge engine — math, science, geography, history, nutrition, finance, and more. Get answers as text, spoken audio, LLM-optimized data, or full structured results.
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

- [awesome-mpp](https://github.com/mbeato/awesome-mpp) - The MPP registry — 100+ Machine Payments Protocol tools, SDKs, services, and payment methods across 15+ chains. The definitive directory for Stripe + Tempo agent payments.
- [mpp-sample](https://github.com/mashharuki/mpp-sample) - Machine Payments Protocolのサンプルコードです.
- [tiktok-mpp-api](https://github.com/mf336/tiktok-mpp-api) - TikTok scraper API powered by Machine Payments Protocol (MPP).
- [mpp-webrtc](https://github.com/mizanxali/mpp-webrtc) - AI agents that pay per-second to watch live video feeds through machine payments protocol (MPP) over webRTC.
- [mpp-sdk](https://github.com/solana-foundation/mpp-sdk) - Solana payment method for the Machine Payments Protocol.
- [mppfinance-sdk](https://github.com/mppfinance/mppfinance-sdk) - Virtual Visa cards for AI agents — powered by Machine Payments Protocol.
- [a2a-mpp-sdk](https://github.com/dahlinomine/a2a-mpp-sdk) - TypeScript SDK for implementing the Machine Payment Protocol (MPP) for automated commerce between AI agents.
- [mpp-settlement-engine](https://github.com/dahlinomine/mpp-settlement-engine) - A lightweight implementation of the Machine Payment Protocol (MPP) for sub-cent agent-to-agent service settlements.
- [mpp-core-contracts](https://github.com/dahlinomine/mpp-core-contracts) - Solidity implementation of the Machine Payment Protocol for autonomous agent-to-agent settlement.
- [mpp-wallet-js](https://github.com/dahlinomine/mpp-wallet-js) - A lightweight TypeScript SDK for implementing the Machine Payment Protocol (MPP) in autonomous agent wallets.
- [tempo-hackathon](https://github.com/kphed/tempo-hackathon) - Dossier: Research-as-a-service over MPP. Ask a question, get cited research. One cent. Includes native MCP server support. Built in <2 hours for the Tempo.xyz hackathon.
- [agent-payments-landscape](https://github.com/goodmeta/agent-payments-landscape) - Living comparison of agent payment protocols: AP2, ACP, x402, MPP, UCP. Verified claims with primary sources.
- [knox](https://github.com/stephancill/knox) - A moddable payments CLI for x402 and MPP.
- [gateway](https://github.com/tomopay/gateway) - Payment gateway for MCP tools — charge agents per tool call (withPayments()). Supports x402, MPP, Stripe.
- [tomopay-gateway](https://github.com/QuinnYates/tomopay-gateway) - Payment gateway for MCP servers — monetize your tools with one wrapper. Supports x402, MPP, and Stripe.
- [agent-commerce-protocol](https://github.com/nicoroldan1/agent-commerce-protocol) - ACE (Agent Commerce Exchange) — Open protocol for agent-native commerce: discovery, trust, and catalog for the agentic web. Payment-agnostic (x402, MPP, Stripe).
- [ows-react-native](https://github.com/rkmonarch/ows-react-native) - The first React Native library for the Open Wallet Standard (OWS) — policy-gated autonomous payments on Solana using USDC, with Stripe MPP / x402 HTTP 402 support.
- [flow-core](https://github.com/achilliesbot/flow-core) - Unified IAM pre-execution gateway. One call replaces MemGuard + NoLeak + EP + RiskOracle. x402/MPP payment gate, unified proof hash.
- [mpp-bazaar](https://github.com/ethanmlam/mpp-bazaar) - Food truck ordering API with dynamic pricing powered by the Machine Payments Protocol (MPP). The thing x402 can't do.
- [PayRep](https://github.com/NadirEcho/PayRep) - Merchant trust scores for AI agent payments — MPP + x402.
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
