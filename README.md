# solana_mint
## Create wallet
https://docs.metaplex.com/guides/cli-wallet
```
solana-keygen new --outfile ~/.config/solana/devnet.json
```

The next step is to make this our default keypair:
```
solana config set --keypair ~/.config/solana/devnet.json
```

and make sure we are on the devnet:
```
solana config set --url https://metaplex.devnet.rpcpool.com/
```

If all the above steps are successful, your configuration be similar to:
```
solana config get
```

Output
```
Config File: ~/.config/solana/cli/config.yml
RPC URL: https://metaplex.devnet.rpcpool.com/
WebSocket URL: wss://metaplex.devnet.rpcpool.com/ (computed)
Keypair Path: ~/.config/solana/devnet.json
Commitment: confirmed
```

In order to add SOL to your devnet wallet, you can request funds from a faucet:
```
solana airdrop 2
```

The solana airdrop command is sometimes unreliable. If the command doesn't work, you can use the airdrop tool at https://solfaucet.com.

## Switching to Mainnet Beta for Production
To switch to the Mainnet Beta cluster, you can either make a new wallet or continue to use the same keypair. This guide will be using the same keypair.

The only step would be to set the cluster to a Mainnet Beta RPC:
```
solana config set --url https://api.metaplex.solana.com/
```

You can check your wallet address:
```
solana address
```

and your balance:
```
solana balance
```

## Candy Machine - Sugar
In the same folder have the "devnet.json" conf file tree and the folder containing the assets, 
https://docs.metaplex.com/developer-tools/sugar/tutorials/my-first-candy-machine

Créer la config
```
sugar create-config
```

Upload Images and Metadata to External Storage
```
sugar upload
```

Deploy a Candy Machine
```
sugar deploy
```

Verify Successful Deployment
```
sugar verify
```

Mint a NFT
```
sugar mint
```

## Config Project Candy Machine
Check informations
```
sugar show
```

Create .env and modify REACT_APP_CANDY_MACHINE_ID

Airdrop some tokens to get started
```
solana airdrop 1 <RECIPIENT_ACCOUNT_ADDRESS> --url https://api.devnet.solana.com
```
