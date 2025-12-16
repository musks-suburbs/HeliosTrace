# HeliosTrace

Built for Base

HeliosTrace is a compact Base-native repository designed to verify wallet connectivity, Base RPC availability, and explorer visibility using official Coinbase and Base tooling.

Rather than focusing on application logic, this project acts as a diagnostic surface for Base infrastructure and account abstraction–friendly UX flows.

## Core Idea

The repository provides a minimal yet expressive signal that:
- a wallet can connect on Base
- Base RPC endpoints are reachable
- onchain state can be read deterministically
- Basescan links resolve correctly for inspection and verification

## Base Networks

Base Mainnet  
- chainId (decimal): 8453  
- Explorer: https://basescan.org  
- RPC: https://mainnet.base.org  

Base Sepolia  
- chainId (decimal): 84532  
- Explorer: https://sepolia.basescan.org  
- RPC: https://sepolia.base.org  

## Application Overview

Primary file: `app/heliosTrace.ts`

At runtime, HeliosTrace:
- boots an OnchainKit provider scoped to the selected Base network
- renders wallet onboarding UI using OnchainKit Wallet
- performs Base JSON-RPC reads via Viem:
  - chainId
  - latest block height
  - native ETH balance for a supplied address
- exposes the relevant Basescan explorer for manual validation

## Repository Structure

- `app/`
  - `heliosTrace.ts`  
    React entry component combining OnchainKit wallet UX with Viem-based Base reads.

Typical auxiliary files:
- `package.json`
- `tsconfig.json`
- `index.html` / `main.tsx`
- `.env` (optional)

## Tooling

OnchainKit  
- Wallet UX components and Base-first primitives  
- https://github.com/coinbase/onchainkit  

Viem  
- EVM client library for Base JSON-RPC reads

## Setup Notes

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run with a standard React/Vite or Next.js dev server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Runtime Flow

1. Launch the app in a browser
2. Select Base Sepolia for validation or Base Mainnet for production reads
3. Connect a wallet using the OnchainKit UI
4. Provide an address to inspect
5. Execute the trace and review onchain results
6. Follow the Basescan explorer links as needed

## Base Mainnet Deployment

Deployed on Base Mainnet

Network: Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Deployed contract address:  
your_adress  

Basescan deployment and verification links:
- Contract address:  
  https://basescan.org/address/your_adress  
- Contract verification (source code):  
  https://basescan.org/address/your_adress#code  

## Author

GitHub: https://github.com/musks-suburbs 

Public contact (email): 01_musks.suburbs@icloud.com 

Public contact (X): https://x.com/memuro3270

## License

MIT License

## Testnet Deployment (Base Sepolia)

To validate behavior against a live Base test environment, up to three reference contracts may be deployed on Base Sepolia.

**Network:** Base Sepolia  
**chainId (decimal):** 84532  
**Explorer:** https://sepolia.basescan.org  

**Contract #1 address:**  
0x9D7f580F8FA3eC424bD1aC5470c68A74941D6a05

Deployment and verification:
- https://sepolia.basescan.org/address/0x9D7f580F8FA3eC424bD1aC5470c68A74941D6a05 
- https://sepolia.basescan.org/0x9D7f580F8FA3eC424bD1aC5470c68A74941D6a05/0#code  
