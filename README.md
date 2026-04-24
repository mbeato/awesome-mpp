# Awesome MPP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, tools, SDKs, and services for the Machine Payments Protocol (MPP) -- the open standard for AI agent payments and machine-to-machine commerce.

## Contents

- [Protocol and Specs](#protocol-and-specs)
- [SDKs](#sdks)
- [Payment Methods](#payment-methods)
- [Framework Integrations](#framework-integrations)
- [Infrastructure and Proxies](#infrastructure-and-proxies)
- [Agent Tools and CLIs](#agent-tools-and-clis)
- [Middleware and Extensions](#middleware-and-extensions)
- [Services](#services)
- [Community Projects](#community-projects)
- [Tempo Blockchain](#tempo-blockchain)
- [Resources](#resources)

## Protocol and Specs

- [mpp-specs](https://github.com/tempoxyz/mpp-specs) - Official MPP specification using an RFC-style Payment HTTP auth scheme.
- [mpp](https://github.com/tempoxyz/mpp) - Protocol documentation site and service registry.
- [IETF Draft](https://datatracker.ietf.org/doc/draft-ryan-httpauth-payment/) - The `draft-ryan-httpauth-payment` internet-draft by Brendan Ryan (Tempo) and Jeff Weinstein (Stripe).

## SDKs

### Official

- [mppx](https://github.com/wevm/mppx) - TypeScript SDK with server, client, and proxy support. Includes Hono, Express, and Next.js middleware. Also works as a zero-config reverse proxy for payment gating.
- [pympp](https://github.com/tempoxyz/pympp) - Python SDK for MPP.
- [mpp-rs](https://github.com/tempoxyz/mpp-rs) - Rust SDK for MPP.
- [tempo-go](https://github.com/tempoxyz/tempo-go) - Go SDK for Tempo Blockchain with MPP client support.
- [tempo-ts](https://github.com/tempoxyz/tempo-ts) - TypeScript tooling for Tempo, used internally by mppx.

### Community

- [mppx-rb](https://github.com/cjavdev/mppx-rb) - Ruby SDK for MPP.
- [mpp-go](https://github.com/deszhou/mpp-go) - Community Go SDK for MPP.
- [fastapi-mpp](https://github.com/SylvainCostes/fastapi-mpp) - FastAPI middleware for Python.
- [ZenHive/mpp](https://github.com/ZenHive/mpp) - Elixir implementation of MPP.
- [dotnet-sdk-mpp](https://github.com/evenuss/dotnet-sdk-mpp) - .NET SDK for MPP.
- [dart-tempo](https://github.com/Immadominion/dart-tempo) - Dart SDK for Tempo.

## Payment Methods

MPP is payment-method agnostic. Each chain or rail has its own plugin.

### Official Tempo and Stripe

- [mpp-card](https://www.npmjs.com/package/mpp-card) - Fiat card payments for MPP. Tempo stablecoins and Stripe card support are built into mppx.

### Solana

- [@solana/mpp](https://github.com/solana-foundation/mpp-sdk) - Official Solana Foundation SDK for MPP.
- [@dexterai/mpp](https://github.com/Dexter-DAO/dexter-mpp) - Managed settlement with no Blockchain infrastructure needed.
- [mpp-solana](https://github.com/starc007/mpp-solana) - SPL token support for MPP on Solana.
- [mppx-solana](https://github.com/nitishxyz/mppx-solana) - Mppx plugin for Solana.
- [mpp-spl](https://github.com/nullxnothing/mpp-spl) - SPL token and pump.fun payment layer with token registry and Jupiter pricing.
- [solana-mpp](https://github.com/sendaifun/solana-mpp) - Solana extension for MPP.

### Lightning

- [@buildonspark/lightning-mpp-sdk](https://github.com/buildonspark/lightning-mpp-sdk) - Lightning payments via Spark.
- [@ambosstech/lightning-mpp-sdk](https://github.com/AmbossTech/lightning-mpp-sdk) - Lightning with LND and NWC adapters.
- [@axobot/mppx](https://github.com/zbdpay/axobot-mppx) - Lightning-native MPP with pluggable adapters.

### Other Chains

- [@t2000/mpp-sui](https://github.com/mission69b/t2000) - Sui USDC payments.
- [stellar-mpp-sdk](https://github.com/stellar-experimental/stellar-mpp-sdk) - Stellar payment method for MPP.
- [xrpl-mpp-sdk](https://github.com/krkmu/xrpl-mpp-sdk) - XRP Ledger payment method for MPP.
- [mpp-abstract](https://github.com/Abstract-Foundation/mpp-abstract) - Abstract chain with custom intents and escrow.
- [mpp-movement](https://github.com/MoveIndustries/mpp-movement) - Movement Network payment method.
- [mpp-ton](https://github.com/TesseraeVentures/mpp-ton) - TON payment method for MPP.
- [algorand-mpp-sdk](https://github.com/GoPlausible/algorand-mpp-sdk) - Algorand payment method for MPP.
- [mpp-avalanche](https://github.com/ashucoder9/mpp-avalanche) - Avalanche with streaming payment channels.
- [mppx-multiversx](https://github.com/sasurobert/mppx-multiversx) - MultiversX payment method for MPP.
- [mega-mpp-sdk](https://github.com/ifavo/mega-mpp-sdk) - MegaETH payment method for MPP.
- [skalenetwork/mpp-sdk](https://github.com/skalenetwork/mpp-sdk) - SKALE payment method for MPP.
- [zimppy](https://github.com/betterclever/zimppy) - Zcash private payments for AI agents.
- [@0xsquid/mpp](https://www.npmjs.com/package/@0xsquid/mpp) - Cross-chain payments via Squid Router.
- [mppx-stableyard](https://github.com/stableyardfi/mppx-stableyard) - Any chain in, any chain out, with fiat settlement.
- [@monad-crypto/mpp](https://github.com/monad-crypto/mpp) - Monad payment method for MPP.
- [@caypo/mpp-canton](https://www.npmjs.com/package/@caypo/mpp-canton) - Canton Network USDCx payments.
- [xrpl-mpp-stack](https://github.com/lgcarrier/xrpl-mpp-stack) - XRP Ledger Python implementation with charge and session support.
- [@raycashxyz/mpp](https://www.npmjs.com/package/@raycashxyz/mpp) - Private payments via Raycash.
- [@solobank/mpp-solana](https://www.npmjs.com/package/@solobank/mpp-solana) - Solana USDC payment method for MPP.
- [@paytoll/sdk](https://github.com/paytoll/sdk) - Developer toolkit for accepting machine payments on Solana via MPP.

- [Alchemy](https://agents.alchemy.com/) - Blockchain data APIs including Core RPC APIs, Prices API, Portfolio API, and NFT API across 100+ chains.
- [Allium](https://allium.so) - System of record for onchain finance. Real-time Blockchain data: token prices, wallet balances, transactions, PnL, and SQL explorer.
- [Codex](https://codex.io) - Comprehensive onchain data API for tokens and prediction markets. Real-time prices, charts, trades, and wallet analytics across 80+ networks via GraphQL.
- [QuickNode](https://quicknode.com/) - Core Node API for 80+ Blockchains and 140+ networks.
- [Tempo RPC](https://tempo.xyz) - Tempo Blockchain JSON-RPC access (mainnet and testnet).
## Framework Integrations

The mppx TypeScript SDK includes built-in middleware for Hono, Express, Next.js, Elysia, Bun.serve, and Deno.serve. Community integrations extend MPP to additional frameworks.

- [@agentcash/router](https://www.npmjs.com/package/@agentcash/router) - Next.js App Router with MPP, x402, and API key auth.
- [mpp-aws](https://github.com/i-norden/mpp-aws) - AWS infrastructure integration for MPP.

## Infrastructure and Proxies

- [mppx-proxy](https://github.com/starc007/mppx-proxy) - Standalone reverse proxy for MPP.
- [mpp-proxy-cf](https://github.com/tempoxyz/mpp-proxy-cf) - Cloudflare Workers MPP proxy from the Tempo team.
- [openvps](https://github.com/kartojal/openvps) - MPP-powered VPS hosting where AI agents pay for compute.
- [github-mpp-proxy](https://github.com/aLjTap/github-mpp-proxy) - GitHub REST API proxy with MPP payments.
- [mppscan.com](https://mppscan.com) - Transaction explorer and service discovery for MPP.
- [mpp-cloudflare-dynamic-edge-agent](https://github.com/sam00101011/mpp-cloudflare-dynamic-edge-agent) - Dynamic edge agent on Cloudflare Workers.
- [tollbooth](https://github.com/abhay/tollbooth) - Solana payment gateway with MPP, gasless fee relayer, and axum middleware.
- [Code Storage](https://code.storage) - Paid Git repository creation with authenticated clone URLs.
- [asgcard-public](https://github.com/ASGCompute/asgcard-public) - Virtual MasterCards for AI agents with USDC payments via x402 on Stellar.

- [Object Storage](https://objectstorage.dev) - S3/R2-compatible object storage with dynamic per-size pricing.
- [StableUpload](https://stableupload.dev) - Pay-per-upload file hosting and static site hosting with custom domains — 6 month TTL.
## Agent Tools and CLIs

- [incur](https://github.com/wevm/incur) - CLI framework for agents and humans by wevm.
- [incur-rs](https://github.com/tempoxyz/incur-rs) - Rust port of incur.
- [agent-skills](https://github.com/tempoxyz/agent-skills) - Official Tempo agent skill pack.
- [wallet](https://github.com/tempoxyz/wallet) - CLI wallet and HTTP client with built-in MPP support.
- [@kakedashi/paylog](https://www.npmjs.com/package/@kakedashi/paylog) - CLI to view MPP spending history.
- [@heyamiko/amiko-cli](https://www.npmjs.com/package/@heyamiko/amiko-cli) - CLI for the Amiko AI Agent Marketplace.
- [human402](https://github.com/joohhnnn/human402) - Human-facing 402 payment page for MPP.
- [MPP-Inspector](https://github.com/amgb20/MPP-Inspector) - CLI and web dashboard for debugging MPP flows.
- [mcp-protocol-tester](https://github.com/whiteknightonhorse/mcp-protocol-tester) - Universal test suite for MCP servers with dual-rail payment testing.
- [openprice](https://github.com/tldr-wknd/openprice) - Price discovery middleware for the agent economy.
- [x402-proxy](https://github.com/cascade-protocol/x402-proxy) - Auto-pays HTTP 402 responses on Base, Solana, and Tempo. Includes MCP stdio proxy for AI agents and pay-per-token streaming via MPP sessions.
- [knox](https://github.com/stephancill/knox) - Moddable payments CLI for x402 and MPP.
- [@raycashxyz/mpp-pay](https://github.com/raycashxyz/mpp-pay) - CLI for making paid API requests via MPP.
- [satring](https://github.com/toadlyBroodle/satring) - Service directory for the agent economy with L402 and x402 discovery, ratings, and Lightning payments.
- [regent-cli](https://github.com/regent-ai/regent-cli) - CLI for Regent agents with ERC-8004, x402, MPP, ENS, WorldID, and XMTP support.
- [autolaunch](https://github.com/regent-ai/autolaunch) - Uniswap CCA auctions via CLI for agents with revenue splits from x402 and MPP.
- [402Router](https://github.com/obulai/402Router) - Open-source client-side model router for x402 and MPP providers.
- [APIbase](https://github.com/whiteknightonhorse/APIbase) - Universal MCP gateway for AI agents with 413 tools across 123 providers. Pay per call with x402 and MPP.
- [bitrouter](https://github.com/bitrouter/bitrouter) - Agentic proxy for modern agent runtimes with smart routing across LLMs, tools, and agents.
- [agentic-wallet](https://github.com/smukh/agentic-wallet) - Unified CLI for AI agent wallets across Coinbase, Tempo, OpenWallet, and Crossmint. Interactive and non-interactive modes with JSON output and multi-chain support.

- [Parallel](https://parallel.ai) - Web search, page extraction, and multi-hop web research.
## Middleware and Extensions

- [mppx-rate-limit](https://github.com/leigents/mppx-rate-limit) - Rate limiting for MPP routes.
- [mppx-token-gate](https://github.com/douglasborthwick-crypto/mppx-token-gate) - Token-gate routes via signed wallet attestations across 32 chains.
- [agenttax-mppx](https://github.com/AgentTax/agenttax-mppx) - Tax middleware for sales tax and capital gains on AI agent transactions.
- [mpp-integration](https://github.com/observer-protocol/mpp-integration) - Trust and reputation layer for MPP sellers.
- [@moltrust/mpp](https://www.npmjs.com/package/@moltrust/mpp) - W3C DID-based trust score middleware for MPP. Pre-transaction agent verification via MolTrust trust scores. Works with mppx.
- [sardis-guard-mpp](https://github.com/EfeDurmaz16/sardis-guard-mpp) - Financial intelligence for AI agent payments.
- [costillery](https://github.com/wytcab/costillery) - Receipt intelligence for AI agents, auto-capturing MPP and x402 receipts.
- [agentlair-mpp-identity-bridge](https://github.com/piiiico/agentlair-mpp-identity-bridge) - Verifiable agent identity via DIDs and Ed25519 attestations.
- [@clearagent/mpp](https://www.npmjs.com/package/@clearagent/mpp) - Know Your Agent compliance screening for MPP.
- [agent-verifier](https://github.com/goodmeta/agent-verifier) - Agent spending verification with budget caps and cross-agent tracking.
- [secure-exec](https://github.com/achilliesbot/secure-exec) - Sandboxed tool execution oracle with IAM-gated dry-run and x402/MPP payment gate.
- [mpay](https://www.npmjs.com/package/mpay) - TypeScript SDK for the Machine Payments Protocol.
- [clawmpp](https://www.npmjs.com/package/clawmpp) - MPP integration for OpenClaw providing one wallet for every AI service.
- [x402](https://github.com/coinbase/x402) - Coinbase x402 payment protocol with EVM, SVM, and fetch implementations.
- [twitsh](https://github.com/etherlect/twitsh) - X/Twitter data CLI with x402 micropayment handling.
- [@b3dotfun/anyspend-x402](https://github.com/b3-fun/anyspend-x402) - AnySpend x402 implementation with multi-chain support.
- [@relai-fi/x402](https://github.com/web3luka/relai-sdk) - Unified x402 payment SDK for Solana, Base, Avalanche, SKALE, Polygon, and Ethereum.
- [x402-stacks](https://github.com/tony1908/x402Stacks) - x402 payment protocol on Stacks Blockchain.
- [@b3dotfun/anyspend-x402-fetch](https://github.com/b3-fun/anyspend-x402-fetch) - AnySpend x402 fetch client with multi-token support.
- [mppfinance-sdk](https://github.com/mppfinance/mppfinance-sdk) - Virtual Visa cards for AI agents powered by MPP.
- [@atxp/mpp](https://github.com/atxp-dev/sdk) - ATXP MPP support for agent identity and delegation.
- [@grantex/mpp](https://github.com/mishrasanjeev/grantex) - Grantex agent identity and delegation for MPP.
- [@stellar/mpp](https://github.com/stellar/stellar-mpp-sdk) - Stellar Blockchain payment method for MPP.
- [Agent_Attestation](https://github.com/KCorstor/Agent_Attestation) - Agent attestation API with connectivity, income verification, and ID data for x402, MPP, and KYA stacks.
- [trust-layer](https://github.com/ark-forge/trust-layer) - Certifying proxy for agent-to-agent transactions with SHA-256 proof chain and Ed25519 signatures.
- [cipherpay-x402](https://github.com/atmospherelabs-dev/cipherpay-x402) - CipherPay x402 payment integration.
- [x402-MPP-shielded-](https://github.com/amiabix/x402-MPP-shielded-) - Shielded payment integration for x402 and MPP.
- [402-crawler-spec](https://github.com/taskhawk-systems/402-crawler-spec) - Reference crawler and discovery schemas for L402, x402, and MPP paid API endpoints.

- [@x402/evm](https://github.com/x402-foundation/x402) - X402 Payment Protocol EVM Implementation.
- [@suimpp/mpp](https://github.com/mission69b/suimpp) - Sui USDC payment method for the Machine Payments Protocol (MPP).
- [auditor-mcp](https://github.com/xaviersharwin10/soroban_node_0) - MCP server that audits Soroban smart contracts via autonomous x402 / Stripe MPP payments on Stellar Testnet.
## Services

### First-Party

Services with built-in MPP payment support:

- [APIMesh](https://github.com/mbeato/conway) - 90 pay-per-call APIs for AI agents (web-checker, http-status-checker, favicon-checker, microservice-health-check, status-code-checker, regex-builder, +84 more). Supports x402 + MPP.
- [paid-image-api](https://github.com/cepuyut/paid-image-api) - Pay-per-request AI image generation on Tempo.
- [Dtelecom](https://github.com/dteIecom/Dtelecom) - Real-time voice, video, and voice AI with pay-per-use via x402/MPP.
- [Surf](https://surf.cascade.fyi) - Pay-per-use Twitter, Reddit, web, and inference APIs for AI agents with dual-protocol support on Base, Solana, and Tempo.
- [AgentMail](https://agentmail.to) - Email inboxes for AI agents.
- [Browserbase](https://browserbase.com) - Headless browser sessions, web search, and page fetching for AI agents.
- [Dune](https://dune.com) - Query raw transaction data, decoded smart contract events, stablecoin flows, and protocol analytics.
- [Judge0](https://judge0.com) - Online code execution in 60+ programming languages with sandboxed isolation.
- [Modal](https://modal.com) - Serverless GPU compute for sandboxed code execution and AI/ML workloads.
- [ScreenshotOne](https://screenshotone.com) - Website screenshot API for capturing any URL as PNG, JPEG, WebP, or PDF.
- [Billboard](https://x.com/MPPBillboard) - Post to @MPPBillboard on X with dynamic pricing that doubles per post.
- [Clado](https://clado.ai) - People search, LinkedIn enrichment, and deep research for lead generation.

### Proxied via Tempo

Available through Tempo's MPP proxy at mpp.tempo.xyz -- pay with any MPP method:

**AI/ML:** [Anthropic](https://anthropic.com), [OpenAI](https://openai.com), [Google Gemini](https://ai.google.dev), [Mistral AI](https://mistral.ai), [Groq](https://groq.com), [DeepSeek](https://deepseek.com), [Perplexity](https://perplexity.ai), [OpenRouter](https://openrouter.ai), [Replicate](https://replicate.com), [fal.ai](https://fal.ai), [Stability AI](https://stability.ai), [Suno](https://sunoapi.org), [Grok](https://x.ai)

**Data and Search:** [Exa](https://exa.ai), [Firecrawl](https://firecrawl.dev), [Tavily](https://tavily.com), [Brave Search](https://brave.com/search), [Wolfram|Alpha](https://www.wolframalpha.com), [SerpApi](https://serpapi.com), [Diffbot](https://www.diffbot.com), [EDGAR](https://www.sec.gov/developer), [CoinGecko](https://www.coingecko.com), [Alpha Vantage](https://www.alphavantage.co)

**Developer Tools:** [Deepgram](https://deepgram.com), [DeepL](https://www.deepl.com), [Mapbox](https://www.mapbox.com), [Mathpix](https://mathpix.com), [IPinfo](https://ipinfo.io), [Hunter](https://hunter.io), [BuiltWith](https://builtwith.com), [Google Maps](https://developers.google.com/maps)

**Business:** [Apollo](https://www.apollo.io), [RentCast](https://rentcast.io), [SpyFu](https://spyfu.com), [Oxylabs](https://oxylabs.io), [2Captcha](https://2captcha.com), [KicksDB](https://kicks.dev)

**Travel and Weather:** [AviationStack](https://aviationstack.com), [FlightAPI](https://flightapi.io), [GoFlightLabs](https://goflightlabs.com), [OpenWeather](https://openweathermap.org), [StableTravel](https://stabletravel.com)

**Abstract APIs:** [Company Enrichment](https://www.abstractapi.com/api/company-enrichment), [Email Reputation](https://www.abstractapi.com/api/email-reputation-api), [Exchange Rates](https://www.abstractapi.com/api/exchange-rate-api), [Holidays](https://www.abstractapi.com/api/holidays-api), [IBAN Validation](https://www.abstractapi.com/api/iban-validation-api), [IP Intelligence](https://www.abstractapi.com/api/ip-intelligence-api), [Phone Intelligence](https://www.abstractapi.com/api/phone-validation-api), [Timezone](https://www.abstractapi.com/api/time-date-timezone-api), [VAT](https://www.abstractapi.com/api/vat-validation-rates-api), [Web Scraping](https://www.abstractapi.com/api/web-scraping-api)

**Other Services:** [PostalForm](https://www.postalform.com), [StableEmail](https://stableemail.com), [StableEnrich](https://stableenrich.com), [StablePhone](https://stablephone.com), [StableSocial](https://stablesocial.com), [StableStudio](https://stablestudio.com), [StableUpload](https://stableupload.com), [Prospect Butcher](https://prospectbutcher.com)

## Community Projects

### Agent Frameworks

- [tempo-mpp-agent-starter](https://github.com/efidal/tempo-mpp-agent-starter) - Mainnet-first MPP automation starter.
- [Ottie](https://github.com/jiayaoqijia/Ottie) - Self-evolving agent for Ethereum and crypto.
- [mpp-agentkit](https://github.com/0xOsiris/mpp-agentkit) - World Agent Kit library for MPP.
- [spire](https://github.com/suverenum/spire) - Home for AI agent wallets.
- [Caypo](https://github.com/anilkaracay/Caypo) - Agent finance on institutional rails with MPP, USDCx, and MCP.
- [OpenAgentPay](https://github.com/alokemajumder/OpenAgentPay) - Open-source payment orchestration with 17 packages, 14 routing strategies, and 8 payment connectors.
- [helix](https://github.com/adrianhihi/helix) - Self-healing infrastructure for AI agent payments with 90% auto-recovery.
- [helix-tempo](https://github.com/adrianhihi/helix-tempo) - Self-healing payment SDK for agents on Tempo.
- [agentmart](https://github.com/teckedd-code2save/agentmart) - Autonomous agent-to-agent economy where agents hire agents.
- [clawdmarket](https://github.com/trillskillz/clawdmarket) - Agent-to-agent marketplace with no human intervention required.
- [Masumi-MPP-Bridge](https://github.com/Sarthib7/Masumi-MPP-Bridge) - Universal payment gateway for MPP-enabled agents on Masumi Network.
- [universal-pay](https://github.com/Bobbaybuilding/universal-pay) - Universal 402 payment skill via Across crosschain bridging.
- [a2a-mpp-sdk](https://github.com/dahlinomine/a2a-mpp-sdk) - TypeScript SDK for automated agent-to-agent commerce via MPP.
- [mpp-settlement-engine](https://github.com/dahlinomine/mpp-settlement-engine) - Lightweight sub-cent agent-to-agent settlement engine for MPP.
- [mpp-core-contracts](https://github.com/dahlinomine/mpp-core-contracts) - Solidity contracts for autonomous agent-to-agent settlement via MPP.
- [mpp-wallet-js](https://github.com/dahlinomine/mpp-wallet-js) - Lightweight TypeScript SDK for MPP in autonomous agent wallets.
- [agent-wallet](https://github.com/Sortis-AI/agent-wallet) - Command-line wallet for AI agents with MPP and Solana support.
- [DRAIN](https://github.com/kimbo128/DRAIN) - Decentralized runtime for AI networks with trustless micropayments for AI agents.
- [boltzpay](https://github.com/leventilo/boltzpay) - Multi-protocol, multi-chain payment fetch wrapper for AI agents.
- [settlegrid](https://github.com/lexwhiting/settlegrid) - Settlement layer for AI agent payments with per-call billing, 10 protocols, and built-in discovery.
- [marc](https://github.com/marc-protocol/marc) - Privacy layer for agent payments using FHE-encrypted tokens, agent identity, and escrow-based commerce.

### MCP Bridges

- [mpp-mcp](https://github.com/leigents/mpp-mcp) - Turn MCP server tools into paid endpoints via MPP.
- [mpp-bundler](https://github.com/vikram14s/mpp-bundler) - Claude Code plugin to scaffold MPP billing into any API.
- [shopgraph](https://github.com/laundromatic/shopgraph) - Product data enrichment MCP server with Stripe MPP.
- [tempo-mcp](https://github.com/arome3/tempo-mcp) - MCP server for autonomous stablecoin payments on Tempo.
- [mcp-pay](https://github.com/neul-labs/mcp-pay) - Payment awareness layer for MCP.
- [delx-protocol](https://github.com/davidmosiah/delx-protocol) - Open-core protocol surfaces for MCP, A2A, REST, x402, and MPP.
- [gateway](https://github.com/tomopay/gateway) - Payment gateway for MCP tools, charging agents per tool call with x402, MPP, and Stripe support.
- [tomopay-gateway](https://github.com/QuinnYates/tomopay-gateway) - Payment gateway for MCP servers to monetize tools with one wrapper.
- [402index-mcp-server](https://github.com/ryanthegentry/402index-mcp-server) - MCP server for 402 Index with discovery across 15,000+ paid API endpoints.
- [agentpay-mcp](https://github.com/up2itnow0822/agentpay-mcp) - Non-custodial x402 MCP payment layer for AI agents.

### Applications

- [zk-proof-service](https://github.com/Himess/zk-proof-service) - ZK proof generation with pay-per-Groth16-proof via MPP.
- [privagent-service](https://github.com/Himess/privagent-service) - Privacy-preserving payment proofs via Tempo.
- [content-for-machines](https://github.com/xlxqxs/content-for-machines) - Pay-per-access content gating for AI agents.
- [video-gen-mpp](https://github.com/lucas-walsh/video-gen-mpp) - Video generation with MPP payments.
- [onlygate-tempo-mpp-wrapper](https://github.com/Kenny50/onlygate-tempo-mpp-wrapper) - Zero-trust human-in-the-loop wrapper for MPP spending controls.
- [trenchcoat-mpp](https://github.com/Keeeeeeeks/trenchcoat-mpp) - Agent-powered UberEats ordering using MPP.
- [mpp-uniswap-agent](https://github.com/eek-uniswap/mpp-uniswap-agent) - Autonomous agent pipeline from ETH to Uniswap to USDC to MPP to LLM inference.
- [remlo](https://github.com/winsznx/remlo) - Borderless enterprise payroll on Tempo L1.
- [presto](https://github.com/mmashiat/presto) - Storefront layer for MPP-compatible agent services.
- [TheMinutes](https://github.com/xfajarr/TheMinutes) - Service router for AI agents on Tempo, discovering and routing to 100+ MPP services.
- [tempo-private-payments](https://github.com/zhivkoto/tempo-private-payments) - Confidential stablecoin transfers via stealth addresses and MPP.
- [tiktok-mpp-api](https://github.com/mf336/tiktok-mpp-api) - TikTok scraper API powered by MPP.
- [mpp-webrtc](https://github.com/mizanxali/mpp-webrtc) - AI agents that pay per-second to watch live video feeds over WebRTC.
- [mpp-bazaar](https://github.com/ethanmlam/mpp-bazaar) - Food truck ordering API with dynamic pricing powered by MPP.
- [PayRep](https://github.com/NadirEcho/PayRep) - Merchant trust scores for AI agent payments via MPP and x402.
- [flow-core](https://github.com/achilliesbot/flow-core) - Unified IAM pre-execution gateway with x402/MPP payment gate.
- [ows-react-native](https://github.com/rkmonarch/ows-react-native) - React Native library for the Open Wallet Standard with MPP and x402 support on Solana.
- [agent-commerce-protocol](https://github.com/nicoroldan1/agent-commerce-protocol) - Open protocol for agent-native commerce covering discovery, trust, and catalog for the agentic web.
- [agent-payments-landscape](https://github.com/goodmeta/agent-payments-landscape) - Living comparison of agent payment protocols including AP2, ACP, x402, MPP, and UCP.
- [tempo-hackathon](https://github.com/kphed/tempo-hackathon) - Research-as-a-service over MPP with cited results for one cent per query.
- [PotPuzzle](https://github.com/Devendra116/PotPuzzle) - Real-time multiplayer word puzzles with Tempo MPP payments and winner-takes-all rewards.
- [tempo-research-agent](https://github.com/HOWTOREP/tempo-research-agent) - AI research agent where every tool call is a real payment on Tempo via MPP.
- [nba-bets](https://github.com/Ujjwal-N/nba-bets) - Real-time NBA micro-betting with on-chain USDC settlement via Tempo and MPP.
- [ghost-kitchen](https://github.com/max-digi/ghost-kitchen) - Agentic B2B payments demo with multi-hop MPP cascades, virtual debit cards, and DoorDash delivery.
- [voicempp](https://github.com/dieutx/voicempp) - Voice-as-a-Service for AI agents via Tempo MPP with TTS and STT micropayments.
- [tempo-agent-payments-demo](https://github.com/glabun002/tempo-agent-payments-demo) - Agent-to-agent payments on Tempo Blockchain with autonomous AI agents transacting via MPP.
- [tweetclaw](https://github.com/Xquik-dev/tweetclaw) - Full X/Twitter automation via OpenClaw with 120 endpoints and pay-per-call pricing.
- [lorem-ipsum-api](https://github.com/stephancill/lorem-ipsum-api) - Paywalled lorem ipsum API supporting x402 and MPP.
- [arkapi](https://github.com/PiHiker/arkapi) - Anonymous pay-per-call APIs for agents and developers funded with Bitcoin over Ark.
- [agentic-commerce-research](https://github.com/minddog/agentic-commerce-research) - Living research paper on agentic commerce updated daily.
- [doli](https://github.com/doli-network/doli) - Peer-to-peer electronic cash system based on verifiable time.

- [StableTravel](https://stabletravel.dev) - Pay-per-request travel APIs — flights, hotels, activities, transfers, and real-time flight tracking. Powered by Amadeus and FlightAware.
- [Stripe Climate](https://stripe.com/climate) - Fund permanent carbon removal projects via Stripe Climate.
- [StableEmail](https://stableemail.dev) - Pay-per-send email delivery, forwarding inboxes, and custom subdomains — no API keys or accounts.
- [StableEnrich](https://stableenrich.dev) - Pay-per-request research APIs — people, companies, web search, scraping, places, social media, and contact enrichment.
- [StablePhone](https://stablephone.dev) - AI phone calls, dedicated phone numbers, and iMessage/FaceTime lookup — pay per request.
- [StableSocial](https://stablesocial.dev) - Pay-per-request social media data from TikTok, Instagram, Facebook, and Reddit.
- [StableStudio](https://stablestudio.dev) - Pay-per-generation AI image and video creation — Nano Banana, GPT Image, Grok, Flux, Sora, Veo, Seedance, and Wan.
- [PostalForm](https://postalform.com) - Print and mail real letters and documents via AI agents.
- [Prospect Butcher](https://www.prospectbutcher.com) - Order sandwiches for pickup in Brooklyn — the first food purchase made entirely by an AI agent.
### Demos and Examples

- [stellar-mpp-demo](https://github.com/stellar-experimental/stellar-mpp-demo) - Stellar chat via micropayments.
- [mpp-card-charge-demo](https://github.com/armsteadj1/mpp-card-charge-demo) - Interactive card charge flow.
- [MPP_Visa-TAP_PoC](https://github.com/freedomfighter-007/MPP_Visa-TAP_PoC) - MPP combined with Visa TAP proof of concept.
- [example-mega-mpp-cf](https://github.com/ifavo/example-mega-mpp-cf) - MegaETH MPP on Cloudflare Workers.
- [mpp-one-payment](https://github.com/delineas/mpp-one-payment) - TypeScript single payment example.
- [tempo-demos](https://github.com/kwattana/tempo-demos) - AI agents making autonomous payments with DoorDash, Shopify, and GPU Marketplace demos.
- [OPK-MPP-Tempo-Hackathon](https://github.com/zhangzhongnan928/OPK-MPP-Tempo-Hackathon) - OPK Pay Terminal combined with MPP for human and machine commerce.
- [tempo-x402-demo](https://github.com/compusophy/tempo-x402-demo) - Interactive x402 demo on Tempo.
- [emv-tempo](https://github.com/zhangzhongnan928/emv-tempo) - EMV contactless card payments settled on Tempo.
- [mpp-sample](https://github.com/mashharuki/mpp-sample) - Sample code demonstrating the Machine Payments Protocol.
- [Stellar-Hackathon](https://github.com/abraham-yusuf/Stellar-Hackathon) - Stellar Hackathon agent with x402 resource integration.

- [awesome-mpp](https://github.com/mbeato/awesome-mpp) - The MPP registry — 100+ Machine Payments Protocol tools, SDKs, services, and payment methods across 15+ chains. The definitive directory for Stripe + Tempo agent payments.
- [mpp-xpr](https://github.com/charliebot87/mpp-xpr) - XPR Network payment method for MPP (Machine Payments Protocol) — zero gas fees, sub-second finality.
- [mpp-sdk](https://github.com/hyli-org/mpp-sdk) - Integration of Hyli for the Machine Payments Protocol.
- [mpp-bds-client](https://github.com/powerloom/mpp-bds-client) - Reference clients for consuming BDS datamarket API (https://bds.powerloom.io) endpoints via the Machine Payment Protocol (MPP).
- [aegis-autonopay](https://github.com/habibafrido/aegis-autonopay) - AI Agent Payment Infrastructure built on Open Wallet Standard (OWS) + x402 + MPP.
- [mpp-agent-demo](https://github.com/mlouie/mpp-agent-demo) - Exploring Tempo's Machine Payments Protocol (MPP) through an agentic DoorDash commerce demo.
- [ASGCompute-ows-agent-pay](https://github.com/ASGCompute/ASGCompute-ows-agent-pay) - ASG Pay - Payment infrastructure for autonomous AI agents. 15 networks (EVM, Stellar, Solana, Stripe MPP), dual protocol (x402 + MPP), fail-closed policy engine. npm: @asgcard/pay.
- [mppx-arc](https://github.com/Himess/mppx-arc) - MPP (Machine Payments Protocol) payment method for Circle's Arc chain — USDC-native charge + session support.
- [robotpostal](https://github.com/intenex/robotpostal) - Physical mail for AI agents. API-first postal service with x402, MPP, and Stripe payments.
- [Starlane](https://github.com/Cassxbt/Starlane) - Dual-rail payment infrastructure for AI agents on Stellar — x402 per-call and MPP payment channels, with a service registry and MCP  interface.
- [Stellect](https://github.com/anilkaracay/Stellect) - The agent payment gateway for Stellar. Smart routing between x402 and MPP — one SDK, any protocol, real USDC settlement.
- [parley](https://github.com/mcevoyinit/parley) - Tiered pricing extension for MPP (Machine Payments Protocol). Agents negotiate the best endpoint tier via HTTP 402.
- [AgentShield](https://github.com/lucarizzo03/AgentShield) - A two-plane orchestration and budget gateway for the Machine Payments Protocol (MPP). Safely delegate Tempo wallet spend to AI agents via cryptographic vouchers.
- [FindMeACitiBike](https://github.com/mmurrs/FindMeACitiBike) - Pick up a bike or find a dock. Real-time Citi Bike availability for NYC — paid per request via Machine Payments Protocol.
- [tempo-agent-treaty](https://github.com/mcevoyinit/tempo-agent-treaty) - Agentic OTC block trading on Tempo chain. AI agents negotiate large trades P2P using Vellum SDK, settled via MPP (Machine Payments Protocol).
- [bkey-ios-x402](https://github.com/fabianbaier/bkey-ios-x402) - BKey iOS SDK — x402/MPP machine-payment support.
- [moltpe-agent-payments](https://github.com/umangbuilds/moltpe-agent-payments) - Payment infrastructure for AI agents. Reference implementation: x402 + MPP + fiat.
- [mppx-hedera](https://github.com/tomrowbo/mppx-hedera) - First native Machine Payments Protocol method for Hedera. Charge + session intents, no facilitator. MIT.
- [hak-mppx-hedera-plugin](https://github.com/tomrowbo/hak-mppx-hedera-plugin) - Hedera Agent Kit plugin for Machine Payments Protocol (MPP) — charge and session payments with USDC.
- [Autonomous-X-border-Interchange-System](https://github.com/nugrahsalam/Autonomous-X-border-Interchange-System) - AXIS is an open liquidity API for AI agents built on Stellar Testnet. Any external agent can send XLM to AXIS via MPP (Machine Payments Protocol) and receive the target asset directly in their wallet.
- [tempo-hackathon-round-1](https://github.com/kphed/tempo-hackathon-round-1) - Dossier: Research-as-a-service over MPP. Ask a question, get cited research. One cent. Includes native MCP server support. Built in <2 hours for the Tempo.xyz hackathon.
- [railrouter-lite](https://github.com/vdineshk/railrouter-lite) - Intelligent real-time payment rail router for AI agents. Chooses the optimal rail (Stripe MPP + x402 + Google AP2) in <50ms and compounds routing intelligence in D1.
- [agentpass-skill](https://github.com/cybersecai-uk/agentpass-skill) - First digitally signed Agent Skill for AI agent payments. Signed with x-agent-trust (ECDSA P-256). Supports x402, Stripe, ACP, AP2, MPP, Mastercard Agent Pay, Visa TAP, L402. Apache 2.0.
- [routedock](https://github.com/winsznx/routedock) - Unified payment execution layer for Stellar x402, MPP charge, MPP session behind one client.pay() call.
- [rever-ai](https://github.com/alienworld1/rever-ai) - Credit scores for AI agents. An on-chain reputation layer built on Stellar using x402 and MPP. Agents earn trust through their payment history to unlock lower API rates and sub-5ms session latency. Ze.
- [stellar-agent-mesh](https://github.com/ghost-clio/stellar-agent-mesh) - Agent-to-agent economic infrastructure on Stellar via x402 payments.
## Tempo Blockchain

The payments infrastructure powering MPP:

- [tempo](https://github.com/tempoxyz/tempo) - The Tempo blockchain.
- [tempo-apps](https://github.com/tempoxyz/tempo-apps) - Frontend apps monorepo.
- [tempo-foundry](https://github.com/tempoxyz/tempo-foundry) - Foundry fork with Tempo support.
- [tempo-std](https://github.com/tempoxyz/tempo-std) - Solidity contracts and libraries for Tempo.
- [ledger-app-tempo](https://github.com/tempoxyz/ledger-app-tempo) - Ledger hardware wallet plugin for Tempo.
- [docs](https://github.com/tempoxyz/docs) - Ecosystem documentation.

## Resources

### Documentation

- [mpp.dev](https://mpp.dev) - Protocol documentation and service directory.
- [docs.tempo.xyz](https://docs.tempo.xyz) - Tempo and MPP developer docs.
- [Stripe MPP Announcement](https://stripe.com/blog/machine-payments-protocol) - Stripe's MPP launch announcement.

### Articles

- [The Machine Payments Protocol](https://tempo.xyz/blog/mainnet/) - Tempo mainnet launch and MPP introduction.
- [Stripe Agentic Commerce Solutions](https://stripe.com/blog/introducing-our-agentic-commerce-solutions) - Stripe's broader agent payment strategy.

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## Footnotes

The **Machine Payments Protocol** is an open HTTP payment standard created by Stripe and Tempo Labs, launched March 2026. It uses HTTP 402 (Payment Required) with an extensible challenge-credential-receipt flow so any client -- AI agents, apps, or humans -- can pay for any API or service in the same HTTP request. No API keys, billing accounts, or checkout flows are required. MPP is payment-method agnostic, supporting stablecoins, credit cards, Lightning, and 15+ chains. It supports one-time charges, sessions with pre-authorized spending, and streaming. The IETF draft (`draft-ryan-httpauth-payment`) was co-authored by Stripe and Tempo.
