# meme-innovation-data

# How to add new tvl protocol
1. Go to protocol page on defillama and copy the protocol name
2. Search for protocol data in https://api.llama.fi/protocols.
3. Add slug, id and protocol link into tvl_protocol_list.
```json
    {
      "id": "4967", // <-- id
      "name": "PancakeSwap Options",
      "address": "bsc:0x0E09FaBB73Bd3Ade0a17ECC321fD13a19e81cE82",
      "symbol": "CAKE",
      "url": "https://pancakeswap.stryke.xyz",
      "description": "......",
      "chain": "Arbitrum",
      "logo": "https://icons.llama.fi/pancakeswap-options.jpg",
      "audits": "0",
      "audit_note": null,
      "gecko_id": null,
      "cmcId": null,
      "category": "Options",
      "chains": ["Arbitrum"],
      "oracles": [],
      "forkedFrom": [],
      "module": "pancake-stryke/index.js",
      "audit_links": [],
      "twitter": "PancakeSwap",
      "parentProtocol": "parent#pancakeswap",  // <--- parent protocol
      "listedAt": "...",
      "slug": "pancakeswap-options",  // <-- slug
      "tvl": "...",
      "chainTvls": {
        "Arbitrum": "..."
      },
      "mcap": null
    }
```
4. If the protocol has 'parentProtocol'. Please add all protocol slugs and ids belong to the same parent protocol into object to prevent losing data.


## How to Add a New TVL Protocol

### Step 1: Find the Protocol Name
1. Get the defillama protocol link from provider and go to the protocol page on [DefiLlama](https://defillama.com).

### Step 2: Search for Protocol Data
1. Use the API to find the protocol's data: [https://api.llama.fi/protocols](https://api.llama.fi/protocols).

### Step 3: Add the Protocol to `tvl_protocol_list`
1. Add the protocol's details to `tvl_protocol_list`. Below is an example of the format:

```json
{
    "name": "PancakeSwap",
    "slug": [
      "pancakeswap-amm",
      "pancakeswap-amm-v3",
      "pancakeswap-stableswap",
      "pancakeswap-amm-v1",
      "pancakeswap-perps",
      "pancakeswap-options"
    ],
    "id": [194, 2769, 2529, 2590, 3538, 4967],
    "link": "https://defillama.com/protocol/pancakeswap",
    "enable": true,
    "group": "partA"
  },
```
2. If the protocol has 'parentProtocol' attributes please find all protocols sharing the same parent protocol, and include all slugs and ids into `tvl_protocol_list` to prevent data loss.