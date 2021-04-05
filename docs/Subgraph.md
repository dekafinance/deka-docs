---
id: subgraph
title: Subgraph
sidebar_label: Subgraph
slug: /protocol/subgraph
---
This section explains everything you need to know about the DEKA protocol subgraph. The DEKA protocol subgraph listens for events from one or more data sources (Smart Contracts) on the Binance Smart Chain. It handles indexing and caching of data which can later be queried by the exposed GraphQL API.

The DEKA protocol subgraph is powered by [The Graph](https://thegraph.com/).

:::note 
The Graph is an indexing protocol for querying networks like Binance Smart Chain and IPFS. Anyone can build and publish open APIs, called subgraphs, making data easily accessible.
:::

#### Data Sources

- DEKA Protocol - **TBA**

#### Resources

- DEKA Protocol Subgraph Explorer: [https://thegraph.com/explorer/subgraph/dekafinance/deka](https://thegraph.com/explorer/subgraph/dekafinance/deka)
- DEKA Protocol Subgraph Source: [https://github.com/dekafinance/deka-subgraph](https://github.com/dekafinance/deka-subgraph)

#### Queries

This section provides various query examples. You can test any of the queries, or write your own, on the DEKA protocol subgraph explorer.

```
{
  pools(first: 25) {
    id
    address
    token
  }
  stakes(first: 25) {
    id
    stakeId
    address
    reward
  }
  swaps(first: 25) {
    id
    sender
    amount
    received
    pool
  }
  liquidities(first: 25) {
    id
    sender
    value
    pool
    amount
    amountAlt
  }
}
```