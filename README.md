# 🪙 BBACHAIN Token List

A comprehensive, up-to-date list of tokens deployed on the BBACHAIN blockchain ecosystem.

## 📚 Overview

This repository contains a curated list of tokens on the BBACHAIN network. It serves as a reliable source for applications that need token information, including wallets, DEXs, dashboards, and other DeFi services. The repository maintains separate lists for validated tokens that have passed verification checks and banned tokens that have been flagged for security concerns or other issues.

## 📁 Repository Structure

```
├── lists
│   ├── validated-tokens.json  # List of verified and validated tokens
│   ├── banned-tokens.json     # List of flagged or banned tokens
│   └── images                 # Token logo images
├── node_modules
│   └── typescript             # TypeScript dependency
│       ├── bin                # TypeScript binaries
│       └── lib                # TypeScript libraries
├── src
│   ├── schema                 # JSON schema definitions
│   ├── types                  # TypeScript type definitions
│   └── utils                  # Utility functions
└── test                       # Test files
```

## ✨ Features

- **✅ Verified Tokens**: All tokens in the validated list have undergone verification to ensure legitimacy
- **📋 Comprehensive Metadata**: Includes token symbols, names, decimals, logos, and contract addresses
- **🔄 Regularly Updated**: Maintained and updated to include new tokens as they are deployed
- **👥 Community Driven**: Open for community contributions following our submission guidelines
- **🔧 Strong TypeScript Support**: Fully typed token definitions for developer convenience
- **🛡️ Security Focus**: Includes banned token list to protect users from potentially harmful tokens

## 📄 Token List Format

Our token lists follow this structure:

```json
{
 "name": "Validated Tokens",
 "version": 1,
 "timestamp": "2023-10-01T00:00:00Z",
 "tokens": [
   {
     "name": "Wrapped BBA",
     "symbol": "WBBA",
     "address": "", // Mint address on BBAchain
     "chainId": 1,
     "decimals": 6,
     "logoURI": ""
   },
   {
     "name": "Wrapped ETH",
     "symbol": "WETH",
     "address": "", // Mint address on BBAchain
     "chainId": 1,
     "decimals": 6,
     "logoURI": ""
   }
 ]
}
```

Each token entry in the list includes:

- `name`: Full name of the token
- `symbol`: Token symbol (ticker)
- `address`: Mint address on the BBACHAIN
- `chainId`: Network identifier
- `decimals`: Number of decimal places
- `logoURI`: Path to the token's logo image

### 🚫 Banned Tokens List

The banned tokens list has a similar structure but identifies tokens that have been flagged for security concerns or other issues:

```json
{
 "name": "Banned Tokens",
 "version": 1,
 "timestamp": "2025-04-24T00:00:00Z",
 "tokens": [
   {
     "name": "Test Token",
     "symbol": "TEST",
     "address": "",
     "chainId": 1,
     "decimals": 18,
     "logoURI": ""
   },
   {
     "name": "Test Token 2",
     "symbol": "TEST2",
     "address": "",
     "chainId": 1,
     "decimals": 6,
     "logoURI": ""
   }
 ]
}
```

Applications should check against this list to protect users from potentially harmful tokens.

## 🛠️ Usage

### 👨‍💻 For Developers

You can fetch the token lists directly from our GitHub repository:

```javascript
const validatedTokensURL = 'https://raw.githubusercontent.com/bbachain/token-list/main/lists/validated-tokens.json';
const bannedTokensURL = 'https://raw.githubusercontent.com/bbachain/token-list/main/lists/banned-tokens.json';

// Example using fetch
fetch(validatedTokensURL)
  .then(response => response.json())
  .then(tokenList => {
    // Use the validated token list in your application
    console.log(tokenList);
  });

// Also check banned tokens to protect your users
fetch(bannedTokensURL)
  .then(response => response.json())
  .then(bannedTokens => {
    // Use this list to filter out problematic tokens
    console.log(bannedTokens);
  });
```

### 📝 TypeScript Support

The repository includes TypeScript definitions to provide type safety when working with the token list:

```typescript
import { TokenInfo, TokenList } from '@bbachain/token-list';

// Type definition example
interface TokenInfo {
  name: string;
  symbol: string;
  address: string;
  chainId: number;
  decimals: number;
  logoURI?: string;
}

interface TokenList {
  name: string;
  version: number;
  timestamp: string;
  tokens: TokenInfo[];
}

// Now you have type-safe access to token properties
const tokens: TokenInfo[] = tokenList.tokens;
```

## ➕ Adding a Token

We welcome submissions of new tokens. To add a token to the validated list:

1. 🍴 Fork this repository
2. ✏️ Add your token to the `lists/validated-tokens.json` file
3. 🖼️ Add your token logo to the `lists/images` directory (PNG format, 256x256px recommended)
4. ✅ Verify that your submission passes all validation checks by running the tests
5. 🔄 Create a pull request with a brief description of the token

Note: The `banned-tokens.json` list is maintained by the BBACHAIN team and is not open for direct contributions. If you believe a token has been incorrectly added to this list, please contact the team through our official channels.

### ✅ Requirements

- The token must have a valid mint address on BBACHAIN
- The token must have genuine usage and liquidity 
- The token must have a valid website and social media presence
- Logo must be a PNG with transparent background

## 👨‍💻 Development

### 🚀 Setup

```bash
# Install dependencies
npm install

# Run tests
npm test
```

### ✅ Validation

We provide utilities to validate token entries:

```bash
# Validate token entries
npm run validate
```

## 📜 License

This repository and its contents are licensed under the MIT License.

## 📞 Contact

For questions, suggestions, or help with token submissions:

- 📱 [Telegram](https://t.me/bbachain)
- 🐦 [Twitter](https://twitter.com/bbachain_com)

## 🙏 Acknowledgements

This token list implementation is specifically designed for the BBACHAIN ecosystem, with a focus on security and reliability.