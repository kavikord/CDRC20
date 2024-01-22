# Doginals

A minter and protocol for inscriptions on Dogecoin. 

## ⚠️⚠️⚠️ Important ⚠️⚠️⚠️

Use this wallet for inscribing only! Always inscribe from this wallet to a different address, e.g. one you created with Woof Wallet. This wallet is not meant for storing funds or inscriptions.

## Prerequisites

To use this, you'll need to use your console/terminal and install Node.js on your computer. So please ensure, that you have your 

### Install NodeJS

Please head over to [https://nodejs.org/en/download](https://nodejs.org/en/download) and follow the installation instructions.

### Launch your own RPC 

In order to inscribe, you will need to have access to a Dodgecoin RPC. For example: [https://getblock.io/](https://getblock.io/) provides a service to get access to an RPC.
You will need that for the configuration.

## Setup

### git clone and install

Install by git clone (requires git and node on your computer) 

#### git clone
```
git clone https://github.com/verydogelabs/inscription-wallet.git
```

**or** 

download this [zip file](https://github.com/verydogelabs/inscription-wallet/archive/refs/heads/main.zip) and upack in a directory.

Now open your terminal and change to the directory the sources are installed.
####

```
cd <path to your download / installation>
npm install
``` 

After all dependencies are solved, you can configure the environment:

### Configure environment

Copy a `.env.example` to `.env` and add your node information:

```
NODE_RPC_URL=http://<ip>:<port>
# This is optional if you have an RPC from getblock.io
NODE_RPC_USER=<username>
NODE_RPC_PASS=<password>
TESTNET=false
FEE_PER_KB=500000000
```

You can get the current fee per kb from [here](https://blockchair.com/).

## Funding

Generate a new `.wallet.json` file:

```
node . wallet new
```

Then send DOGE to the address displayed. Once sent, sync your wallet:

```
node . wallet sync
```

If you are minting a lot, you can split up your UTXOs:

```
node . wallet split <count>
```

When you are done minting, send the funds back:

```
node . wallet send <address> <optional amount>
```

## Minting CDRC20

From file:

```
node . mint <RECEIVER_WALLET_ADDR> "text/plain;charset=utf-8" 3330

```
Token name can be changed in doginals.js script
Line 354 : inscription.chunks.push(bufferToChunk('cdrc-20:mint:cdrc=1000'))
