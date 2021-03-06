---
id: smartcontracts
title: Smart Contracts
sidebar_label: Smart Contracts
slug: /protocol/smartcontracts
---

## Addresses

The contracts are currently deployed on the following networks:

### Binance Smart Chain - Mainnet

#### v.1

| Contract      | Address |
| ------------- | ------- |
| DEKA Token    | **0x992d63281EbF61061fd79623F294d0F0296BeF81** |
| DEKA Protocol | **0x88629f11e22861043B2E701207a19Aeb743562F9** |
| DEKA App      | **0xEA9776dAA746d0d29424ff1a251f03c8F95A0693** |

#### v.2

| Contract      | Address |
| ------------- | ------- |
| DEKA Token    | **0xcc043fF110ec01beB2e33C2713Af5924A19aB723** |
| DEKA Protocol | **0x0757733c26f1364Ae096E6F21eeE6281789ab7cD** |
| DEKA App      | **0x9D8d758Bfc999d0404718c7b95381365Aa40C6D5** |

### Binance Smart Chain - Testnet

#### v.1

| Contract      | Address |
| ------------- | ------- |
| DEKA Token    | **0x992d63281EbF61061fd79623F294d0F0296BeF81** |
| DEKA Protocol | **0x88629f11e22861043B2E701207a19Aeb743562F9** |
| DEKA App      | **0xEA9776dAA746d0d29424ff1a251f03c8F95A0693** |

#### v.2

| Contract      | Address |
| ------------- | ------- |
| DEKA Token    | **0xcc043fF110ec01beB2e33C2713Af5924A19aB723** |
| DEKA Protocol | **0x0757733c26f1364Ae096E6F21eeE6281789ab7cD** |
| DEKA App      | **0x9D8d758Bfc999d0404718c7b95381365Aa40C6D5** |

## DEKA Protocol

:::info NOTE
"A handful of individuals control the algorithms of the world. It's time to decentralize." - Tyler Winklevoss
:::

Given the above quote, smart contracts are computer code that define how money moves, so we put the security and simplicity as top priority while building the DEKA protocol.

### State functions

Those are the functions that require transacting on the Binance Smart Chain network.

#### Stake

```jsx
function stake(uint256 amountIn, uint256 days, address receiver, bytes calldata data) external returns (uint256 mintedAmount, uint256 matchedAmount, bytes32 id);
```

#### Unstake

```jsx
function unstake(bytes32 id) external returns (uint256 withdrawAmount);
```

#### Unstake Early

```jsx
function stake(uint256 amountIn, uint256 days, address receiver, bytes calldata data) external returns (uint256 minte
```

### View functions

Those are the functions that can be used to fetch data from the protocol.

#### Get Stake Balance

```jsx
function balances(address staker) external view returns (uint256);
```

#### Get DPY ratio

```jsx
function getDPY(uint256 amountIn) external view returns (uint256);
```

#### Get Mint Amount

```jsx
function getMintAmount(uint256 amountIn, uint256 expiry) external view returns (uint256);
```

#### Get Stake By ID

```jsx
function stakes(bytes32 id) external view returns (uint256 amountIn, uint256 expiry, uint256 expireAfter,
```

## Events

A list of all events emitted by the DEKA protocol.

### Staked

```jsx
event Staked(
    bytes32 id,
    uint256 amountIn,
    uint256 expiry,
    uint256 expireAfter,
    uint256 mintedAmount,
    address indexed staker,
    address indexed receiver
);
```

- **_id_**: _This is the stake id. With the stake id you can fetch the stake data from the protocol._
- **_amountIn_**: _This is the \$DKA amount that the user has staked._
- **_expiry_**: _The time after which the stake will expire (e.g. 86400 = 1 expiration)_
- **_expireAfter_**: _The block timestamp after which the stake will expire._
- **_mintedAmount_**: _The amount of minted $DKA - this is basically the yield being redirected to the DEKA receiver._
- **_taker_**: _The address of the user._
- **_receiver_**: _The address of the yield destination._

### Unstaked

```jsx
event Unstaked(bytes32 id, uint256 amountIn, address indexed staker);
```

- **_id_**: _This is the stake id. With the stake id you can fetch the stake data from the protocol._
- **_amountIn_**: _This is the $DKA amount that the user has staked._
- **_staker_**: _The address of the user._

