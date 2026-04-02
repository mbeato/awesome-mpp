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

- [Parallel](https://parallel.ai) - Web search, page extraction, and multi-hop web research.
## Middleware and Extensions

- [mppx-rate-limit](https://github.com/leigents/mppx-rate-limit) - Rate limiting for MPP routes.
- [mppx-token-gate](https://github.com/douglasborthwick-crypto/mppx-token-gate) - Token-gate routes via signed wallet attestations across 32 chains.
- [agenttax-mppx](https://github.com/AgentTax/agenttax-mppx) - Tax middleware for sales tax and capital gains on AI agent transactions.
- [mpp-integration](https://github.com/observer-protocol/mpp-integration) - Trust and reputation layer for MPP sellers.
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

## Services

### First-Party

Services with built-in MPP payment support:

- [APIMesh](https://github.com/mbeato/conway) - 27 pay-per-call APIs for AI agents including web-checker, SEO audit, email verification, and more. Supports x402 and MPP.
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

### MCP Bridges

- [mpp-mcp](https://github.com/leigents/mpp-mcp) - Turn MCP server tools into paid endpoints via MPP.
- [mpp-bundler](https://github.com/vikram14s/mpp-bundler) - Claude Code plugin to scaffold MPP billing into any API.
- [shopgraph](https://github.com/laundromatic/shopgraph) - Product data enrichment MCP server with Stripe MPP.
- [tempo-mcp](https://github.com/arome3/tempo-mcp) - MCP server for autonomous stablecoin payments on Tempo.
- [mcp-pay](https://github.com/neul-labs/mcp-pay) - Payment awareness layer for MCP.
- [delx-protocol](https://github.com/davidmosiah/delx-protocol) - Open-core protocol surfaces for MCP, A2A, REST, x402, and MPP.
- [gateway](https://github.com/tomopay/gateway) - Payment gateway for MCP tools, charging agents per tool call with x402, MPP, and Stripe support.
- [tomopay-gateway](https://github.com/QuinnYates/tomopay-gateway) - Payment gateway for MCP servers to monetize tools with one wrapper.

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

- [StableTravel](https://stabletravel.dev) - Pay-per-request travel APIs — flights, hotels, activities, transfers, and real-time flight tracking. Powered by Amadeus and FlightAware.
- [Stripe Climate](https://stripe.com/climate) - Fund permanent carbon removal projects via Stripe Climate.
- [StableEmail](https://stableemail.dev) - Pay-per-send email delivery, forwarding inboxes, and custom subdomains — no API keys or accounts.
- [StableEnrich](https://stableenrich.dev) - Pay-per-request research APIs — people, companies, web search, scraping, places, social media, and contact enrichment.
- [StablePhone](https://stablephone.dev) - AI phone calls, dedicated phone numbers, and iMessage/FaceTime lookup — pay per request.
- [StableSocial](https://stablesocial.dev) - Pay-per-request social media data from TikTok, Instagram, Facebook, and Reddit.
- [StableStudio](https://stablestudio.dev) - Pay-per-generation AI image and video creation — Nano Banana, GPT Image, Grok, Flux, Sora, Veo, Seedance, and Wan.
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

- [awesome-mpp](https://github.com/mbeato/awesome-mpp) - The MPP registry — 100+ Machine Payments Protocol tools, SDKs, services, and payment methods across 15+ chains. The definitive directory for Stripe + Tempo agent payments.
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
