# Solana Airdrop and Enrollment Project

This project demonstrates basic Solana wallet operations including creating a keypair, requesting an airdrop, and transferring SOL on Solana's devnet. It culminates in enrolling in the Turbin3 prerequisite program using the Anchor framework.

## Prerequisites

- Node.js
- Yarn
- Basic understanding of Typescript
- (Windows users should use WSL2 for Solana development)

## Installation

1. Create a new project directory and initialize:
```bash
mkdir airdrop && cd airdrop
yarn init -y
```

2. Install dependencies:
```bash
yarn add @types/node typescript @solana/web3.js bs58 @coral-xyz/anchor prompt-sync
yarn add -D ts-node
```

3. Initialize TypeScript configuration:
```bash
yarn tsc --init --rootDir ./ --outDir ./dist --esModuleInterop --lib ES2019 --module commonjs --resolveJsonModule true --noImplicitAny true
```

## Project Structure

The project consists of four main scripts:
- `keygen.ts`: Generates a new Solana keypair
- `airdrop.ts`: Requests SOL tokens from devnet
- `transfer.ts`: Transfers SOL between wallets
- `enroll.ts`: Enrolls in the Turbin3 prerequisite program

## Usage

### 1. Generate a New Keypair
```bash
yarn keygen
```
This will generate a new Solana wallet and output the public key and private key. Save the private key in a `dev-wallet.json` file.

### 2. Request Airdrop
```bash
yarn airdrop
```
Requests 2 devnet SOL tokens to your generated wallet.

### 3. Transfer SOL
```bash
yarn transfer
```
Transfers 0.1 SOL to your Turbin3 wallet address.

### 4. Empty Wallet
Update the transfer script with the provided code to empty your devnet wallet into your Turbin3 wallet.

### 5. Enroll in Turbin3
```bash
yarn enroll
```
Submits your enrollment in the Turbin3 prerequisite program on devnet.

## Important Notes

1. Create a `.gitignore` file to exclude wallet files:
```
*wallet.json
```

2. The Turbin3 prerequisite program is deployed at:
```
WBAQSygkwMox2VuWKU133NxFrpDZUBdvSBeaBEue2Jq
```

3. When working with the enrollment program, ensure your GitHub account name is correctly specified in the enrollment script.

## Security Considerations

- Never commit wallet files to git repositories
- Keep your private keys secure
- Use separate wallets for development and production
- Clean up unused devnet accounts as a best practice

## Program Concepts

### Program Derived Address (PDA)
PDAs are used to enable programs to "sign" transactions with a deterministic public key. They combine:
- A seed (in this case, "prereq")
- The signer's public key
- A bump to ensure the address is off the elliptic curve

### Interface Definition Language (IDL)
The IDL defines the program's interface, including:
- Account structures
- Instructions
- Error codes

## Troubleshooting

If you encounter issues:
1. Ensure you're connected to Solana devnet
2. Verify your wallet files are correctly formatted
3. Check that you have sufficient SOL for transactions
4. Verify your GitHub account name is correctly entered for enrollment
