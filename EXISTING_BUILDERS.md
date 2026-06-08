# Guide for Builders Who Already Started

You do not need to migrate or restart. Do these three things only.

## 1. Add .env.example to your repo root

Copy the .env.example file from this template into your project root.
Edit it to match your actual environment variables.
Confirm .env is in your .gitignore. If real keys have already been
committed, rotate them immediately before pushing anything else.

## 2. Verify your hardhat.config.js targets Fuji

Your fuji network block must look exactly like this:

```javascript
fuji: {
  url: "https://api.avax-test.network/ext/bc/C/rpc",
  chainId: 43113,
  accounts: process.env.PRIVATE_KEY ? [process.env.PRIVATE_KEY] : [],
},
```

Run: npx hardhat compile

## 3. Add GitHub topics to your repo

Go to your repo on GitHub, click the gear icon next to About, and add:
  avalanche  mini-hack  web3-kenya  fuji-testnet

Add m-pesa if your project integrates M-Pesa.
Add solidity if it includes smart contracts.

## Weekly submissions

Branch format:  week-{N}-{your-github-handle}
PR title:       [Cohort X Week N] Your Name - Deliverable title
PR target:      main branch of your own repo (not this template)
Deadline:       Sunday midnight EAT
Submit:         PR link in #submissions on Discord
