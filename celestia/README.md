# Celestia Node
Golang implementation of Celestia's data availability node types (`light` | `full` | `bridge`).

## Node types
- Bridge nodes - relay blocks from the celestia consensus network to the celestia data availability (DA) network
- Full nodes - fully reconstruct and store blocks by sampling the DA network for shares
- Light nodes - verify the availability of block data by sampling the DA network for shares
More information can be found [here](https://github.com/celestiaorg/celestia-node/blob/main/docs/adr/adr-003-march2022-testnet.md#legend).

## Hardware requirements
- Bridge nodes - 16 GB RAM (minimum), 6 cores CPU, 10 TB SSD Storage, 1 Gbps for Download/1 Gbps for Upload
- Full nodes - 16 GB RAM (minimum), 6 cores CPU, 10 TB SSD Storage, 1 Gbps for Download/1 Gbps for Upload
- Light nodes - 500 MB RAM (minimum), Single Core CPU, 100 GB SSD Storage, 56 Kbps for Download/56 Kbps for Upload

## Docker Images
- Mainnet Beta (celestia) - ghcr.io/celestiaorg/celestia-node:v0.14.1
- Mocha - ghcr.io/celestiaorg/celestia-node:v0.15.0
- Arabica - ghcr.io/celestiaorg/celestia-node:v0.16.0-rc0

## Quick Start
SDL in this repository configured as `light` node and `celestia` network. Modify environment if needed and deploy on Akash. More information can be found [here](https://docs.celestia.org/nodes/docker-images).

## cURL JSON-RPC
Example request:

`
curl -H "Content-Type: application/json" -X POST -d
'{"id": 1,
  "jsonrpc": "2.0",
  "method": "header.SyncState",
  "params": []
}' http://localhost:26658
`

More methods ca be found [here](https://node-rpc-docs.celestia.org/?version=v0.14.1).
