# Slate bootstrap file (main) - 90199

### How to install

### Bootstrap the Blockchain Synchronization

Normally the Slate client will download the transaction and network information, called the blockchain, from the network by syncing with the other clients. This process can take quite some time as the [Slate blockchain](https://blockchain.info/charts/blocks-size) is growing bigger and bigger for each day. Luckily there is a safe and fast way to speed up this process. We'll show you how to bootstrap your blockchain to bring your client up to speed in just a few simple steps.

### Requirements

- A fresh install of the slate client software.

**For Windows users:**
Open explorer, and type into the address bar:

	%APPDATA%\Slate
    
This will open up the data folder. It should look like the image below. Copy over the bootstrap.dat from your download folder to this directory.

**For OSX users:**
Open Finder by pressing Press [shift] + [cmd] + [g] and enter:

	~/Library/Application Support/Slate/
    
**For Linux users:**
The directory is hidden in your User folder. Go to:

	~/.slate/
    
### Importing the blockchain
Now start the Slate client software. It should show "Importing blocks from disk".

Wait until the import finishes. The client will download the last days not covered by the import. Congratulations you have successfully imported the blockchain!

### Is this safe?

Yes, the above method is safe. The download contains only raw blockchain data and the client verifies this on import. Do not download the blockchain from unofficial sources, especially if they provide `*.rev` and `*.sst` files. These files are not verified and can contain malicious edits.

### How to create my own bootstrap?

The block files are in the same format as the bootstrap file. Their format is really simple: just concatenate all blocks after prefixing them by the network number (to avoid mixing the testnets) and the block length. 

        [network number] [length] [block header] [block transactions]
        [network number] [length] [block header] [block transactions]
        [network number] [length] [block header] [block transactions]

### How to create my own bootstrap on Linux/Mac (method 2)?

We simply cat all blk000*.dat files into bootstrap.dat

    1. Open terminal
    1. Go to the folder where the blocks are. In this case Slate's folder (it's the same for other slate forks)

            ```            
            cd "Library/Application Support/Slate/blocks/"
            ```

    1. concatenate all the blk files
            
            ```        
            cat blk000*.dat > bootstrap.dat
            ```

    1. Done.

### How to create my own bootstrap on Windows (method 2)?

Making your own bootstrap.dat is simple in windows, just run this command from your datadir/blocks dir

    ```
    Copy /b blk00000.dat+blk00001.dat+blk00002.dat bootstrap.dat
    ```

This batch script can make your life easier on windows, you need to run it from datadir/blocks directory:

    ```
    @echo off 
    setlocal enableDelayedExpansion 

    set SLATEDATADIR=%APPDATA%\Slate\blocks
    for /F %%x in ('dir /B/D/ON %SLATEDATADIR%\blk*.*') do (
      IF NOT [!B!] == [] set B=!B!+
      set FILENAME=%SLATEDATADIR%\%%x
      set B=!B!"!FILENAME!"
    )
    copy /b %B% bootstrap.dat
    ```

### Links - How to create my own bootstrap file

  - **How to for Windows, Linux and Mac users**
    - For [Linux/Mac](./../../#how-to-create-my-own-bootstrap-on-linuxmac-method-2) users
    - For [Windows](./../../#how-to-create-my-own-bootstrap-on-windows-method-2) users
  - For advanced users - [manually](./../../#how-to-create-my-own-bootstrap)

Bootstrap file (_bootstrap.dat_)
 - Block height: `90199`
 - Block hash: `4480d89de6711113608aa5cb5db8b17788fb81d01f91f10afbb272e83a017bd5`
 - Tx: `180497`
 - Date: `2018-07-21 14:11:52`
 - Date (epoch): `1532182312`
 - Progress: `1.000007`
 - Cache: `62`

### Block 90199
```
{
  "hash": "dc344ac9467f96b9dcd1716adecbf7fd97067f1602a12b5efcb7a83dcb3521d9",
  "confirmations": 8,
  "size": 569,
  "height": 90199,
  "version": 2,
  "merkleroot": "254632820daca23a521628344611bc8b188d80da984ed4fa270c40006a57aa36",
  "acc_checkpoint": "14f07c370ae71178465c22e302b4e614f2c6e4ae6dfe6bc8d1cd53f464da2a23",
  "tx": [
    "33341412fec2ff396dcdfd8523f51ce54a8677dda057d1b86628b66d91b02ffd",
    "25a0fe0e57ca6fbd4c941cc3312b3160d8b44c0addc07d01f9cc7f927e51defb"
  ],
  "time": 1532182312,
  "nonce": 0,
  "bits": "192c1aa8",
  "difficulty": 97380951.66611773,
  "chainwork": "00000000000000000000000000000000000000000000003036a7515903ef758e",
  "previousblockhash": "bc2264004fe2ae841bfb8caf903568e145a968a306c5c94d506ed4a33138bb0e",
  "nextblockhash": "e41679e1cc2f6209b36dde40587064e917d49d4f682f5b05f8a0d1b8c621f74d",
  "moneysupply": 9499999998.76938975,
  "zSLXsupply": {
    "1": 33.00000000,
    "5": 75.00000000,
    "10": 240.00000000,
    "50": 750.00000000,
    "100": 3100.00000000,
    "500": 7000.00000000,
    "1000": 24000.00000000,
    "5000": 255000.00000000,
    "total": 290198.00000000
  }
}
```

### Genesis block
```
{
  "hash": "00000feb03167c4a4fa9f2bafcaea0e9f7e5646330e13c69e7ffa2dce58ace44",
  "confirmations": 90207,
  "size": 290,
  "height": 0,
  "version": 1,
  "merkleroot": "80290404060ff7ff5bc6a42f755d24f6087ba5685474a5c8ffafac65de8b2bbf",
  "acc_checkpoint": "0000000000000000000000000000000000000000000000000000000000000000",
  "tx": [
    "80290404060ff7ff5bc6a42f755d24f6087ba5685474a5c8ffafac65de8b2bbf"
  ],
  "time": 1524496461,
  "nonce": 67657104,
  "bits": "1e0ffff0",
  "difficulty": 0.000244140625,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000100010",
  "nextblockhash": "000002f68dbbf1fcfacb8f0b4e64083efdd2f07a906728ee068d573ffa5bcb4e",
  "moneysupply": 0.00000000,
  "zSLXsupply": {
    "1": 0.00000000,
    "5": 0.00000000,
    "10": 0.00000000,
    "50": 0.00000000,
    "100": 0.00000000,
    "500": 0.00000000,
    "1000": 0.00000000,
    "5000": 0.00000000,
    "total": 0.00000000
  }
}
```

### What is actually bootstrap.dat file?

In 2012, the Bitcoin blockchain was growing to 10+ gigabytes and downloading the entire chain from the p2p network was taking an excessive amount of time (multiple days) due to inefficiencies in the way nodes shared block data. In order make it easier to setup a full node, a snapshot of the blockchain data [was distributed](https://bitcointalk.org/index.php?topic=145386.0) by [Jeff Garzik](https://github.com/jgarzik) as a file named bootstrap.dat using BitTorrent. Starting with version 0.8 bitcoind will load and validate initial blockchain data from any file named bootstrap.dat found in its [data directory](https://en.bitcoin.it/wiki/Data_directory#Default_Location).

Today, this is actually slower than syncing normally. In Bitcoin Core version 0.10.0+ the p2p sync process was dramatically improved making it faster than using the bootstrap.dat file. This bootstrapping process is therefore obsolete and discouraged.
