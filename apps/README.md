# Apps

Off-chain apps to interact with the mixer

## client

The [`client` CLI][client], is the primary way to interact with the mixer. It has two commands `deposit` and `withdraw` which work as expected. Most of the args can be loaded from env vars.

`deposit` produces a spending key which is written to std-out.

`withdraw` requires a single positional argument <SPENDING_KEY> which is the hex encoded spending key produced by a call to deposit.

### Usage

Run the `client` with:

```sh
cargo run --bin client
```

```text
$ cargo run --bin client -- --help

Usage: client [OPTIONS] --chain-id <CHAIN_ID> --eth-wallet-private-key <ETH_WALLET_PRIVATE_KEY> --rpc-url <RPC_URL> --contract <CONTRACT> <COMMAND>

Commands:
  deposit   Deposit N eth into the contract and generate the withdrawal key
  withdraw  Withdraw N eth from the contract using the withdrawal key
  help      Print this message or the help of the given subcommand(s)

Options:
      --chain-id <CHAIN_ID>
          Ethereum chain ID [env: CHAIN_ID=]
      --eth-wallet-private-key <ETH_WALLET_PRIVATE_KEY>
          Ethereum wallet private key [env: ETH_WALLET_PRIVATE_KEY=]
      --rpc-url <RPC_URL>
          Ethereum Node endpoint [env: RPC_URL=]
      --contract <CONTRACT>
          Application's contract address on Ethereum [env: CONTRACT=]
      --contract-deploy-height <CONTRACT_DEPLOY_HEIGHT>
          The height at which the contract was deployed [default: 0]
      --note-size <NOTE_SIZE>
          The note size, N, used by this contract in wei [default: 1000000000000000000]
  -h, --help
          Print help
  -V, --version
          Print version
```
