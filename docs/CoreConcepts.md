---
id: coreconcepts
title: Core Concepts
sidebar_label: Core Concepts
slug: /protocol/coreconcepts
---

## DEKA Token
The $DKA token is a Binance Smart Chain (BEP20) token that enables interacting with the DEKA protocol.

The DEKA token does not have a fixed supply. $DKA is minted on every stake, and it's burned on every unstake (only if the staking period has not been elapsed). The process of minting can only be achieved using the DEKA protocol.

The token's inflation rate is correlated to the usage of DEKA protocol, the DPY (Deka Percentage Yield), and the matching ratio.

The token follows the BEP20 standard with few extensions:
- Transfer with authorization, which enables gasless transactions (ERC-3009).
- An exposed `mint()` and `burn()` functions which can be invoked only by the DEKA protocol.

## DEKA Stake
DEKA stakes are a way to stake your $DKA for certain amount of time and get upfront yield instantly.

For end-users, staking is intuitive: a user picks an amount and staking time and the protocol calculates how much yield they’ll receive. The user can also pick the destination of the yield - this can be any valid BEP20 address.

### Anatomy of a stake
At the most basic level all stakes in the DEKA Protocol happen with a single function, named `stake`.

```jsx 
function stake(uint256 amountIn, uint256 expiry, address receiver, bytes calldata data)
```

- **_amountIn_**: _This is the $DKA amount that the user is going to stake._
- **_expiry_**: _The time after which the stake will expire._
- **_receiver_**: _The address of the yield destination - externally owned accounts or a contract._
- **_data_**: _Arbitrary data passed to the receiving contract - it’s up to the dApp what kind of data is passed._


## DEKA Receiver
Whenever a user stake he can choose the destination of the yield. The yield destination, can be either externally owned account (EOA) or a smart contract. If the yield destination is an EOA, then the yield is simply transferred to this address.

However, if the yield destination is a contract, then a specific contract interface is invoked. This functionality allows anyone to build their own dApp with their own deka receiver on top of the DEKA protocol.

### Anatomy of the receiver
If the receiver is a contract, the following interface should be exposed by that contract.

```jsx 
function receiveDeka(
    bytes32 id,
    uint256 amountIn,
    uint256 expireAfter,
    uint256 mintedAmount,
    address staker,
    bytes calldata data)
external returns (uint256);
```
- **_id_**: _This is the stake id. With the stake id you can fetch the stake data from the protocol._
- **_amountIn_**: _This is the $DKA amount that the user has staked._
- **_expireAfter_**: _The time after which the stake will expire._
- **_mintedAmount_**: _The amount of minted $DKA - this is basically the yield being redirected to the DEKA receiver._
- **_staker_**: _The address of the user._
- **_data_**: _Arbitrary data passed from the protocol - it’s up to the dApp what kind of data is passed._

