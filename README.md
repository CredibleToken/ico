# CredibleToken Smart Contracts

This repository holds the source code used to generate the ERC20 CredibleToken (CET) smart contract, and
smart contracts used to generate our tokensale smart contracts.

## Basic information
- Type: ERC20
- Symbol: CET
- Decimal: 18

CredibleToken uses a forked version of [TokenMarketNet](https://github.com/TokenMarketNet/ico) open source ICO contracts. 

TokenMarketNet contracts are well respected and have been used by:
- AppCoins
- Civic
- Storj
- Monaco
- DENT
- Ethos
- ixLedger

TokenMarketNet contracts have been publicly audited by:
- [Dala](https://www.iosiro.com/dala-token-sale-audit)
- [Civic](https://medium.com/@ZeppelinOrg/a91754ab6e4b)

## TokenMarketNet contracts used by CredibleToken

### SafeMathLibExt
For Safe unsigned safe math.

### MintedTokenCappedCrowdsaleExt
ICO crowdsale contract that is capped by amount of tokens - tokens are dynamically created during the crowdsale.

### CrowdsaleTokenExt
Used to generate a crowdsaled ERC20 token contract.
 
 An ERC20 token designed specifically for crowdsales with investor protection and further development path.
  - The token transfer() is disabled until the crowdsale is over
  - The token contract gives an opt-in upgrade path to a new contract
  - The same token can be part of several crowdsales through approve() mechanism
  - The token can be capped (supply set in the constructor) or uncapped (crowdsale contract can mint new tokens)

### FlatPricingExt

Fixed crowdsale pricing - everybody gets the same price.

### NullFinalizeAgentExt

A finalize agent that does nothing - token transfer must be manually released by the owner

### ReservedTokensFinalizeAgent

The default behavior for when the crowdsale ends - unlock tokens.

### Registry

Registry of contracts deployed from Token Wizard owned by the address owner.