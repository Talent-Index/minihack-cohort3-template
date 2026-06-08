# Mini Hack Cohort 3 — Agentic AI Systems on Avalanche
> Team1 Kenya | 2026 | Technical Lead: Joseph Njoroge (Scotch)

[![Status](https://img.shields.io/badge/Cohort%203-Upcoming-555?style=flat-square)](https://team1-kenya-mini-hack.vercel.app)
[![Network](https://img.shields.io/badge/Network-Avalanche%20Fuji-e84142?style=flat-square)](https://testnet.snowtrace.io)
[![Stack](https://img.shields.io/badge/Stack-Claude%20API%20%7C%20ethers.js%20%7C%20RAG%20%7C%20Hardhat-333?style=flat-square)](#tools)

Fork this repo to your personal GitHub account. Build an autonomous AI agent that connects to Avalanche. Deploy it to a public URL. Present at Builders Connect.

---

## Prerequisite

Cohort 3 requires Cohort 1 completion or equivalent knowledge. Equivalent means you can demonstrate:

- Deploying a Solidity smart contract to Fuji testnet using Hardhat
- Sending transactions and reading contract state using ethers.js
- Writing async/await Node.js with error handling and external API calls
- Understanding of REST API design and JSON data structures

If you completed Cohort 1, you are ready. Cohort 2 completion is not required but helps with on-chain thinking.

---

## What you will build

An autonomous AI system that reasons about on-chain data and can take actions. By Week 4 you will have a Claude API tool-calling agent, a blockchain-aware wallet advisor that reads Fuji data, a RAG knowledge base built from your own documents, and a proof-of-concept autonomous USDC payment trigger with human-in-the-loop safety controls.

This is the frontier track. Agents that touch real transaction flows require safety-first design — human confirmation steps, spending limits, kill switches, and audit logs are graded requirements, not optional extras.

---

## Session schedule

| Day | Time | Platform | What happens |
|-----|------|----------|-------------|
| Tuesday | 8:00 PM EAT | Google Meet | New concepts, live coding, hands-on exercises |
| Thursday | 8:00 PM EAT | Google Meet | Second teaching block — select Thursdays include guest practitioners |
| Thursday | 6:00 PM EAT | Discord voice | Office hours — bring your blockers before the main session |

Google Meet link is pinned in Discord `#announcements`.

---

## Getting started

### 1. Fork this repository

Click **Use this template** or **Fork**. Fork to your personal GitHub account.

### 2. Clone and set up

```bash
git clone git@github.com:YOUR-HANDLE/minihack-cohort3-template.git
cd minihack-cohort3-template
npm install
cp .env.example .env
npx hardhat compile
```

### 3. Get Fuji testnet AVAX

Visit [core.app/tools/testnet-faucet](https://core.app/tools/testnet-faucet). You need AVAX for the on-chain components in Weeks 2 through 4.

---

## Accounts to create before Week 1

| Account | Link | Notes |
|---------|------|-------|
| GitHub | github.com | Use your real name |
| Avalanche Builders Hub | core.app/builders-hub | Quest 1 — primary KPI, create this first |
| Core Wallet on Fuji | core.app | Required for on-chain work |
| Alchemy | alchemy.com | Free tier — Fuji transaction history APIs for Week 2 |
| Anthropic Console | console.anthropic.com | Claude API key — required from Week 1 |

Fuji testnet RPC:
```
RPC URL:   https://api.avax-test.network/ext/bc/C/rpc
Chain ID:  43113
Explorer:  https://testnet.snowtrace.io
```

**Important on API costs:** The Anthropic API is pay-per-token. Claude Haiku is the cheapest model — use it for development and testing. Claude Sonnet for final submissions where response quality matters. Set a spend limit on your Anthropic account before you start to avoid unexpected charges.

---

## Weekly workflow

```bash
git checkout main
git pull origin main
git checkout -b week-{N}-{your-github-handle}
```

PR title format:
```
[Cohort 3 Week N] Your Name - Deliverable title
```

Submit PR link in Discord `#submissions` and complete quests on Plug and Play — both due Sunday midnight EAT.

---

## Weekly deliverables and quests

### Week 1 — AI and LLM fundamentals

**Sessions:**
- Tuesday: What are large language models and how they work at a practical level. The difference between a chatbot and an agent. Prompt engineering fundamentals — system prompts, temperature, context windows, token costs. Setting up the Anthropic Claude API. Building a first CLI chatbot in Node.js.
- Thursday: Function calling and tool use — giving an LLM the ability to take actions. Building a tool-calling agent that can perform a web search and summarise results. Error handling in agentic loops. Connecting agents to real data sources. Overview of the agentic landscape in 2026.

**Deliverable:** A CLI agent built with the Claude API that can answer questions using at least one external tool (web search, calculator, or a custom function you write). Submit: GitHub repo with README and a recorded terminal demo.

**Quests (Plug and Play — due Sunday midnight EAT):**

| Quest | Task |
|-------|------|
| Q1 | Create or verify your Builders Hub account — submit a screenshot of your active profile |
| Q2 | Complete the "Intro to AI Development" or nearest equivalent module on Avalanche Academy and upload your certificate |
| Q3 | Build and run your Week 1 CLI agent — submit your GitHub repo link |
| Q4 | Post in Discord `#week-1-cohort3`: describe one real Kenyan use case where an AI agent could replace a manual process |
| Q5 | Write a system prompt for an agent that helps a small Kenyan merchant manage their inventory — submit as a GitHub gist |

---

### Week 2 — On-chain data and blockchain-aware agents

**Sessions:**
- Tuesday: Querying on-chain data programmatically — Alchemy enhanced APIs, The Graph subgraph queries, direct RPC calls. Structuring blockchain data for LLM consumption. Building an agent that reads a wallet's Fuji transaction history and produces a plain-language summary.
- Thursday: Wallet behaviour analysis with AI — identifying patterns, flagging anomalies, summarising DeFi activity. Building a smart wallet advisor that connects to Core Wallet, reads balances and history, and gives AI-powered insights. What decisions should an AI never make autonomously on-chain, and how to design human-in-the-loop checkpoints.

**Deliverable:** An agent that connects to a Fuji wallet address (read-only), retrieves its transaction history via Alchemy or The Graph, and returns a structured AI-generated summary including balance, recent activity, and notable patterns. Submit: GitHub repo, README, and a sample output screenshot.

**Quests (Plug and Play — due Sunday midnight EAT):**

| Quest | Task |
|-------|------|
| Q1 | Complete the "Avalanche Developer Tooling" module on Avalanche Academy and upload your certificate |
| Q2 | Set up an Alchemy account and make a successful API call to retrieve Fuji transaction history — submit a screenshot |
| Q3 | Build and submit your Week 2 wallet advisor agent GitHub repo |
| Q4 | Write 3 sentences in Discord `#week-2-cohort3` on what human-in-the-loop means for an autonomous payment agent |
| Q5 | Find one real-world example of an AI agent that made a bad financial decision and post a summary in Discord |

---

### Week 3 — RAG, knowledge bases, and agentic payments

**Sessions:**
- Tuesday: Retrieval-augmented generation — what it is and why agents need it. Embedding documents using an embedding model. Vector databases — storing and retrieving embedded content with Chroma. Building a knowledge agent that answers questions from a custom document set. Chunking and indexing strategies.
- Thursday: Autonomous payment agents on Avalanche — agents that initiate USDC transfers after verifying a condition. Designing safe autonomous payment logic — pre-flight checks, spending limits, kill switches, and audit logs. Connecting agent decisions to ethers.js transaction calls. Logging all AI-triggered on-chain actions. AvaRamp architecture as a reference for AI payment routing.

**Deliverable:** An agent with a RAG knowledge base built from at least 5 documents (your project README, Avalanche docs, Daraja API docs, or similar). The agent answers questions from those documents. Additionally, a proof-of-concept payment trigger: an agent that evaluates a simple condition and initiates a USDC transfer on Fuji if met, with a human-confirmation step before signing. Submit: all repos, vector store setup script, and a recorded demo.

**Safety requirement:** Your autonomous payment trigger must include all of the following or it will not pass the integration depth criterion:
- A human confirmation step before any transaction is signed
- A maximum spending limit hardcoded in the agent logic
- An audit log of every AI decision that leads to a transaction call
- A kill switch that disables transaction capability without requiring a code change

**Quests (Plug and Play — due Sunday midnight EAT):**

| Quest | Task |
|-------|------|
| Q1 | Complete the "Advanced Avalanche Development" or nearest module on Avalanche Academy and upload your certificate |
| Q2 | Build your RAG agent and submit the GitHub repo link |
| Q3 | Run your autonomous payment trigger on Fuji testnet and submit the Snowtrace transaction link |
| Q4 | Write a 1-page safety design doc for your agentic payment system — what checks exist before a transaction fires |
| Q5 | Post your biggest technical blocker this week in Discord `#week-3-cohort3` and help at least one other builder unblock theirs |

---

### Week 4 — Build sprint, deployment, and Demo Day

**Sessions:**
- Tuesday: No new content. Full build sprint. Focus: productionising the agent — error handling, rate limiting, cost controls. Deploying to Railway or Vercel. Making it accessible via a public endpoint. Technical lead runs check-in slots on Discord voice.
- Thursday: Final testing. Demo rehearsal — each builder walks through their agent live: what it does, how it connects to Avalanche, what it decides autonomously, where humans remain in control. Cohort retrospective. Preparation for Builders Connect.

**Deliverable (Final project):** A deployed agentic AI system accessible via a public URL. Must connect to Avalanche (read or write), use an LLM for reasoning, and include at least one agentic loop where the agent takes an action based on its reasoning. Submit: GitHub repo, deployed URL, architecture diagram, and a 5-minute demo video.

**Demo Day:** Builders Connect — last Saturday of the month. Each builder presents: what your agent does, how it connects to Avalanche, what it decides autonomously, and where humans remain in control. Mandatory for graduation.

**Quests (Plug and Play — due Sunday midnight EAT):**

| Quest | Task |
|-------|------|
| Q1 | Deploy your final agentic system and submit the public URL |
| Q2 | Submit your GitHub repo with README covering: what your agent does, how it connects to Avalanche, its safety constraints |
| Q3 | Upload your 5-minute demo video link |
| Q4 | Complete the cohort exit survey on Plug and Play |
| Q5 | Write a 3-sentence reflection on what you would build next if you had one more month — post in Discord `#cohort3-reflections` |

---

## Assessment rubric

| Criterion | Weight | Excellent | Good | Needs work |
|-----------|--------|-----------|------|------------|
| Functionality | 35% | Agent operates correctly end-to-end | Core agentic loop works | Partial or broken |
| Integration depth | 25% | LLM + on-chain read/write + RAG + safety controls | Two layers integrated | Single component only |
| Code quality | 20% | Clean, commented, error-handled, tested | Readable, some structure | Hard to follow, no tests |
| Documentation | 10% | Full README + architecture diagram + demo | README present | Minimal docs |
| Demo presentation | 10% | Live agent demo with safety walkthrough | Demo works with notes | Slides only |

**Grade bands:** Distinction 90-100% / Merit 75-89% / Pass 60-74% / Incomplete below 60%

Week 4 final project = 40% of cohort grade. Weeks 1-3 = 60% combined.

---

## Submission policy

- **Deadline:** Sunday midnight EAT for PR link and quests
- **Late — up to 48 hours:** Accepted with 20% penalty
- **Late — beyond 48 hours:** Zero for that week
- **Three consecutive zeros:** Removal from cohort without certificate
- **Week 4 pairs:** Allowed — both builders listed in PR, both present at Builders Connect

---

## Resources

**AI and agents**
- Anthropic Claude API: [docs.anthropic.com](https://docs.anthropic.com)
- Anthropic Console (API keys): [console.anthropic.com](https://console.anthropic.com)

**On-chain data**
- Alchemy Avalanche APIs: [docs.alchemy.com/reference/avalanche-api](https://docs.alchemy.com/reference/avalanche-api)
- The Graph: [thegraph.com/docs](https://thegraph.com/docs)

**Avalanche**
- Docs: [docs.avax.network](https://docs.avax.network)
- Builders Hub: [core.app/builders-hub](https://core.app/builders-hub)
- Core Wallet: [core.app](https://core.app)
- Fuji faucet: [core.app/tools/testnet-faucet](https://core.app/tools/testnet-faucet)
- Snowtrace Fuji: [testnet.snowtrace.io](https://testnet.snowtrace.io)
- USDC on Avalanche: [developers.circle.com/stablecoins/usdc-on-avalanche](https://developers.circle.com/stablecoins/usdc-on-avalanche)

**Smart contracts**
- Hardhat: [hardhat.org/docs](https://hardhat.org/docs)
- ethers.js: [docs.ethers.org](https://docs.ethers.org)
- OpenZeppelin: [docs.openzeppelin.com/contracts](https://docs.openzeppelin.com/contracts)

**Programme**
- Handbook: [team1-kenya-mini-hack.vercel.app](https://team1-kenya-mini-hack.vercel.app)
- Discord: linked from the landing page

---

## Help

Post in Discord `#help` with: what you are trying to do, what you tried, and the exact error message.

Office hours: Thursdays 6:00 PM to 7:00 PM EAT on Discord voice.

Tag `@scotch` only after posting in `#help` and not getting a response within a reasonable time.
