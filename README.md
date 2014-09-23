# Alef-bitcoin bounty
 
The following algorithm is build to reduce the fee of multiple transaction using an aggregation technique

### Dependencies
 * bitcoind
 
### Strategy
The  method used is by waiting for transaction to accumulate during a time period than use the aggregation algorithm to produce optimize large transactions

### The algorithm goes as follows:

 * aggregate all shared inputs into single transactions
 * calculate maximal change for each transaction ( with no fees )
 * build transaction acumiltivly whatching transaction size
 * once optimal transaction size is reached continue
 * remove minimal fees from the built transaction
 * aggregate all shared outputs
 * create the actual bitcoin transaction
 * sign the transaction using all the needed private keys
 * repeat the build stage for all transactions left
 * wait 168 hours for the next time to run the script


### Running
Fisrt you need to change the credentails to access the bitcoind server
```
bitcoind = ServiceProxy("http://lior:lior1@127.0.0.1:8332")
```   

Then you need to change the mock function

```
txs = get_transaction_log()
``` 

To get transactions from the actual api

Than just run main.py