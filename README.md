

# Foundry Smart Contract Lottery

This is a web3 project which deploys a provably fair lottery system on blockchain. 



- [Foundry Smart Contract Lottery](#foundry-smart-contract-lottery)
- [Getting Started](#getting-started)
  - [Requirements](#requirements)
  - [Quickstart](#quickstart)
- [Usage](#usage)
  - [Start a local node](#start-a-local-node)
  - [Library](#Install-Libraries)
  - [Deploy](#deploy)
  - [Testing](#testing)
    - [Test Coverage](#test-coverage)
- [Deployment to a testnet or mainnet](#deployment-to-a-testnet-or-mainnet)
- [Thank you!](#thank-you)

# Getting Started

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [foundry](https://getfoundry.sh/)


## Quickstart

```
git clone https://github.com/Gloryjaw/Foundry-Lottery-Project
cd Foundry-Lottery-Project
forge build
```



# Usage

## Start a local node

```
make anvil
```

## Install Libraries

```
make install
```

## Deploy

This will default to your local node. You need to have it running in another terminal in order for it to deploy.

```
make deploy
```


## Testing


```
forge test
```

or

```
forge test --fork-url <Url of testnet>
```

### Test Coverage

```
forge coverage
```

# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `SEPOLIA_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file.

- `PRIVATE_KEY`: The private key of your account (like from [metamask](https://metamask.io/)).

- `SEPOLIA_RPC_URL`: This is url of the sepolia testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

1. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some testnet ETH. You should see the ETH show up in your metamask.

2. Deploy

```
make deploy ARGS="--network sepolia"
```

This will setup a ChainlinkVRF Subscription for you. If you already have one, update it in the `scripts/HelperConfig.s.sol` file. It will also automatically add your contract as a consumer.

3. Register a Chainlink Automation Upkeep

[Follow the documentation and setup the automation for perform upkeep](https://docs.chain.link/chainlink-automation/compatible-contracts)



## Entering the lottery

After deploying to a testnet or local net, you can interact with them

Using cast

```
cast send <RAFFLE_CONTRACT_ADDRESS> "enterRaffle()" --value 0.1ether --private-key <PRIVATE_KEY> --rpc-url $SEPOLIA_RPC_URL
```



# Thank you!

Thank you Patrick collins and Cyfrin team for this amazing project.
