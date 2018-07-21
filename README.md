# Slate bootstrap file (testnet) - 23439

### How to install

### Bootstrap the Blockchain Synchronization

Normally the Slate client will download the transaction and network information, called the blockchain, from the network by syncing with the other clients. This process can take quite some time as the [Slate blockchain](https://blockchain.info/charts/blocks-size) is growing bigger and bigger for each day. Luckily there is a safe and fast way to speed up this process. We'll show you how to bootstrap your blockchain to bring your client up to speed in just a few simple steps.

### Requirements

- A fresh install of the slate client software.

**For Windows users:**
Open explorer, and type into the address bar:

	%APPDATA%\Slate\testnet4
    
This will open up the data folder. It should look like the image below. Copy over the bootstrap.dat from your download folder to this directory.

**For OSX users:**
Open Finder by pressing Press [shift] + [cmd] + [g] and enter:

	~/Library/Application Support/Slate/testnet4
    
**For Linux users:**
The directory is hidden in your User folder. Go to:

	~/.slate/testnet4/
    
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
            cd "Library/Application Support/Slate/testnet4/blocks/"
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

    set SLATEDATADIR=%APPDATA%\Slate\testnet4\blocks
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
 - Block height: `23439`
 - Block hash: `47bc8de5908b6d1fa8866465f33b15bc431332cc7d6fc9c4ce6c151fe98075fa`
 - Tx: `46853`
 - Date: `2018-07-21 14:51:01`
 - Date (epoch): `1532184661`
 - Progress: `0.999922`
 - Cache: `46557`

### Block 23439
```
{
  "hash": "47bc8de5908b6d1fa8866465f33b15bc431332cc7d6fc9c4ce6c151fe98075fa",
  "confirmations": 23,
  "size": 569,
  "height": 23439,
  "version": 2,
  "merkleroot": "63d3519d20303811c402f5cbdaba7e4c8a15a83a34c360a90e5be325e4b4e132",
  "acc_checkpoint": "53951b9e72977cab4742a4a48b88bb3f9cae816b2a74f5fd8fac8d1c85ceb518",
  "tx": [
    "384525c128368943314b0706fa41e5aa7a72dedb20eb6e404ba136220a4a5190",
    "c174df7b940034b7f4ee0fc1219cbc2226df79054ebcbffaa975ad063754ccba"
  ],
  "time": 1532184661,
  "nonce": 0,
  "bits": "1a01269f",
  "difficulty": 14577713.03925858,
  "chainwork": "000000000000000000000000000000000000000000000036e6cc5f4ecc662e6f",
  "previousblockhash": "59da9555da92ef227f74bc903e168f463b6dd3b9480983f2a413b06338f365c8",
  "nextblockhash": "7e3cedcc3ad4d201f9524bec584eb3a71f09bb0f54219ac7c00ab3a1d1a358a0",
  "moneysupply": 949999999.99891330,
  "zSLXsupply": {
    "1": 11.00000000,
    "5": 40.00000000,
    "10": 80.00000000,
    "50": 400.00000000,
    "100": 800.00000000,
    "500": 4000.00000000,
    "1000": 7000.00000000,
    "5000": 40000.00000000,
    "total": 52331.00000000
  }
}
```

### Genesis block
```
{
  "hash": "0000065432f43b3efb23bd0f63fe33d00d02a5f36233fe1b982c08274d58ef12",
  "confirmations": 738,
  "size": 290,
  "height": 0,
  "version": 1,
  "merkleroot": "80290404060ff7ff5bc6a42f755d24f6087ba5685474a5c8ffafac65de8b2bbf",
  "acc_checkpoint": "0000000000000000000000000000000000000000000000000000000000000000",
  "tx": [
    "80290404060ff7ff5bc6a42f755d24f6087ba5685474a5c8ffafac65de8b2bbf"
  ],
  "time": 1524496461,
  "nonce": 846737,
  "bits": "1e0ffff0",
  "difficulty": 0.000244140625,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000100010",
  "nextblockhash": "00000d32b7a30dcff512845caf636f22e8588264e781e94c40ab9ddbd1ba4806",
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
