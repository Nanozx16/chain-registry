# chain-registry

yarn validate evm/{your file.json}
> ```
>
> READ THE GUIDELINES BELLOW CAREFULLY, PAYING PARTICULAR ATTENTION TO THE "features" IN THE [[REQUIREMENT DETAILS](https://github.com/chainapsis/keplr-chain-registry#requirement-details)].
> READ THE GUIDELINES BELLOW CAREFULLY, PAYING PARTICULAR ATTENTION TO THE "features" IN THE [[REQUIREMENT DETAILS for Cosmos-based chains](#cosmos-sdk-based-chain-registration-form-requirement-details)] and [[REQUIREMENT DETAILS for EVM-based chains](#evm-based-chain-registration-form-requirement-details)].

# Guidelines for Community-Driven Non-Native Chain Integration

@@ -23,18 +23,25 @@ Keplr team is now introducing a Community-Driven Integration, which enables our

To make a pull request, please carefully read and follow the guidelines below. Any contribution is more than welcome!

# Cosmos-SDK-based Chains
# Table of Contents

- [Requirements and Preparation](#requirements-and-preparation)
- [Cosmos-SDK-based Chains](#cosmos-sdk-based-chains)
- [EVM-based Chains](#evm-based-chains)
- [Notes](#note)

## Requirements and Preparation
# Requirements and Preparation

This section outlines the basic information that is required for registering a chain to Keplr wallet. Please note that your request does not always guarantee integrations and updates; upon your submission, Keplr team will go through a minimal verification process to see if there is any security issue or any missing information.
This guildline outlines the basic information that is required for registering a chain to Keplr wallet. Please note that your request does not always guarantee integrations and updates; upon your submission, Keplr team will go through a minimal verification process to see if there is any security issue or any missing information.

Once approved, the Keplr browser extension will show the tag “Community-Driven” on the chain connection page, to let the users be aware that the integration was requested and implemented by the community and the Keplr team has gone through the verification process.

<p align="center">
  <img src="https://i.imgur.com/Zp2pthD.png" alt="Sample Image"/>
  <img src="https://i.imgur.com/Zp2pthD.png" alt="Sample Image" style="width: 350px;"/>
</p>

# Cosmos-SDK-based Chains

## Cosmos-SDK-based Chain Registration Directory Structure

chainID is consisted of ({identifier}-{version}). **`chain-identifier`** therefore refers to a text identifier of a chain that comes before its version number. For example:
@@ -133,10 +140,10 @@ Here’s an overview of the structure of the directory. Please provide the infor
- walletUrlForStaking(optional): the URL where the users are directed when they click on Staking button of the Keplr Wallet
- bip44: BIP-44 coin type (118 highly recommended)
- bech32Config: prefix used at the beginning of the address
- currencies: the list of the supported currencies. If your chain uses replicated security, please place your main native token at the top of the currencies list.
- currencies: the list of the supported currencies. If your chain uses replicated security, please place your main native token at the top of the currencies list. Note that IBC tokens are not accepted here.
- feeCurrencies: the list of the tokens that are accepted by the validators for fees
- stakeCurrency: the staking token of the chain. Remove this item if your chain does not support native staking (e.g. your chain uses replicated security) or does not have a staking token.
- coinGeckoId(optional): the active API ID for Keplr to get the price from CoinGecko
- coinGeckoId(optional): the active API ID for Keplr to get the price from CoinGecko. For a testnet chain, this field is not accepted.
- features: any other features that are additionally supported by the chain
  - cosmwasm: supports CosmWasm smart contracts
  - secretwasm: supports WASM smart contracts of Secret Network
@@ -145,17 +152,7 @@ Here’s an overview of the structure of the directory. Please provide the infor
  - axelar-evm-bridge: supports EVM bridge provided by Axelar Network
  - osmosis-txfees: supports paying fees in other currencies on Osmosis


# EVM-based Chains
## Requirements and Preparation

This section outlines the basic information that is required for registering a chain to Keplr wallet. Please note that your request does not always guarantee integrations and updates; upon your submission, Keplr team will go through a minimal verification process to see if there is any security issue or any missing information.

Once approved, the Keplr browser extension will show the tag “Community-Driven” on the chain connection page, to let the users be aware that the integration was requested and implemented by the community and the Keplr team has gone through the verification process.

<p align="center">
  <img src="https://i.imgur.com/Zp2pthD.png" alt="Sample Image"/>
</p>

## EVM-based Chain Registration Directory Structure

@@ -247,14 +244,15 @@ Here’s an overview of the structure of the directory. Please provide the infor
- bip44: BIP-44 coin type (60 highly recommended)
- currencies: the list of the supported currencies. If your chain uses replicated security, please place your main native token at the top of the currencies list.
- feeCurrencies: the list of the tokens that are accepted for fees
- coinGeckoId(optional): the active API ID for Keplr to get the price from CoinGecko
- coinGeckoId(optional): the active API ID for Keplr to get the price from CoinGecko. For a testnet chain, this field is not accepted.
- features: any other features that are additionally supported by the chain
  - op-stack-l1-data-fee: supports paying L1 data fee for OP stack based chain
