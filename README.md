## install go first by using following link
  ``` https://go.dev/doc/install ```

## create a folder for blockchain data
  ``` mkdir devnet && cd devnet ```
  
## Clone the Prysm repository and build the following binaries, which is a PoS
  ``` git clone https://github.com/prysmaticlabs/prysm && cd prysm
      go build -o=../beacon-chain ./cmd/beacon-chain
      go build -o=../validator ./cmd/validator
      go build -o=../prysmctl ./cmd/prysmctl
      cd ..
  ```

## Clone the go-ethereum repository and build it:
  ``` git clone https://github.com/ethereum/go-ethereum && cd go-ethereum
      make geth
      cp ./build/bin/geth ../geth
      cd ..
  ```

## On the Prysm side, create a file called config.yml which is a genesis config for PoS chain
  ```
    CONFIG_NAME: interop
    PRESET_BASE: interop

    # Genesis
    GENESIS_FORK_VERSION: 0x20000089

    # Altair
    ALTAIR_FORK_EPOCH: 2
    ALTAIR_FORK_VERSION: 0x20000090

    # Merge
    BELLATRIX_FORK_EPOCH: 4
    BELLATRIX_FORK_VERSION: 0x20000091
    TERMINAL_TOTAL_DIFFICULTY: 50

    # Capella
    CAPELLA_FORK_VERSION: 0x20000092

    # Time parameters
    SECONDS_PER_SLOT: 12
    SLOTS_PER_EPOCH: 6

    # Deposit contract
    DEPOSIT_CONTRACT_ADDRESS: 0x4242424242424242424242424242424242424242
  ```
  
  ## Create a file called secret.json inside of your devnet folder and enter a secrect key in it
  ### use the following link to create a secret key (optional or use any of urself)
  ```
    https://www.movable-type.co.uk/scripts/sha256.html
  ```
  
 ...continue 
