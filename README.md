# frigate-umbrel

Umbrel app packaging for [Frigate](https://github.com/sparrowwallet/frigate) — Silent Payments Electrum server for Sparrow Wallet.

> Originally maintained by [4rkad](https://github.com/4rkad). Transferred to [semillabitcoin](https://github.com/semillabitcoin) on 2026-05-23. Existing installs continue to receive updates through the original community app store URL — no action required for users.

## Build

```sh
docker build -t frigate-umbrel:dev .
```

## Run standalone (test outside Umbrel)

```sh
docker run --rm \
  -p 57001:57001 \
  -e APP_BITCOIN_NODE_IP=192.168.8.84 \
  -e APP_BITCOIN_RPC_PORT=8332 \
  -e APP_BITCOIN_RPC_USER=frigate \
  -e APP_BITCOIN_RPC_PASS=YOURPASS \
  -e FRIGATE_NETWORK=signet \
  -v $PWD/data:/data \
  frigate-umbrel:dev
```

## Connect Sparrow Wallet (`sp` branch)

- Preferences → Server → Electrum
- URL: `<umbrel-ip>:57001`
- Create wallet with policy type `Single Signature SP (Silent Payments)`
