Set up a private Ethereum node on Linux
Commands
- Creating Folder for Block
• mkdir -p ~/Kaschain/private
• cd ~/Kaschain/private
• pwd
- Creating Genesis Block
• puppeth
- Kaschain (network name)
- Option 2: configure new Genesis
- Option1: Ethhas
- press Enter
- 4224 (Network ID)
- Option 2: Manage existing Genesis
- Option 2: Export genesis configuration
- Press Enter
- Ctrl+C (Exit puppeth)
- Open the genesisblock in editor(atom)
- Initialising Private Node
• geth --datadir ~/Kaschain/private init Kaschain.json
- Creating account
• geth --datadir . account new
• create three accounts using the same command
• list the account details by following command
• ls ./key-store
• geth --datadir . account list
- Start Node
• writing start node script in atom
• atom startnode.sh (write script: start node file in private
directory of Kaschain)
• chmod +x startnode.sh (make it executable after creation)
• ./startnode.sh (run the private node)
Running another console to issue gets commands:
- geth attach
- eth.blockNumber
- eth.pendingTransactions
- eth.getBlock(number)
- admin.nodeInfo
- eth.accounts (to see all accounts)
- eth.coinbase (will show account that will earn mining rewards)
- eth.getBalance(eth.accounts[1]) to see account balances
- eth.getBalance(eth.accounts[0]) this account will show some ether
because it receive mining rewards. it returns wei (min value in
ether currency)
- web3.fromWei(eth.getBalance(eth.accounts[0])) to see ether balance
- web3.fromWei(eth.getBalance(eth.coinbase)) to see ether balance
- miner.stop()
- miner.start() or miner.start(2) seconding mention threads
1- net.version it gives network ID
- personal.unlockAccount(eth.accounts[1], "pass1234", 300) unlock
account for transaction arguments needed are account, password,
time in seconds for unlocking.
- personal.unlockAccount(eth.accounts[2])
Sending ethers from one account to another account
- eth.accounts
- eth.coinbase
- web3.fromWei(eth.getBalance(eth.coinbase), “ether")
- eth.sendTransaction({from: eth.accounts[0], to: eth.accounts[1],
value: web3.toWei(500, “ether")})
- eth.sendTransaction({from: eth.accounts[0], to: eth.accounts[2],
value: web3.toWei(500, "ether")})
- web3.fromWei(eth.getBalance(eth.accounts[1]))
- web3.fromWei(eth.getBalance(eth.accounts[2]))
- web3.fromWei(eth.getBalance(eth.accounts[0]))
- exit
2
