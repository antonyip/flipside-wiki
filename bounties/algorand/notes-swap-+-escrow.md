# NOTES - Swap + Escrow



So here a bit of orders/orderbook concepts from a traditional exchange come into picture

* When you create an order, be it sell or buy type, if it's not a market buy/sell...You are creating an escrow address that holds your bid/ask amount
* If you are market buy/sell, you are trading with someone's escrow address.
* The order/escrow's first txn has the note: OPEN ORDER
* Partial execution is something like: partial fill
* Need to find the case where the escrow/order is fully filled

```
Posting a base64 decoded tx_message:txn:note  
{"LGRN26YU3XVI4FLZPDCDGDHQUMKM2A3CGNOFPGK3CSW7RIE4M3PWYC2P2E-254121594-[execute_partial]_[asa] ":{"orderEntry":"1-3-0-254121594","price":3,"n":1,"d":3,"min":0,"version":7,"escrowAddr":"7KYIOB2AIDIKPQN5QLJQTKQAWKG6GTIOQ7S6G5HSD7D77OIW6QCFYEPAQ4","algoBalance":498000,"asaBalance":14684501,"escrowOrderType":"sell","isASAEscrow":true,"orderCreatorAddr":"LGRN26YU3XVI4FLZPDCDGDHQUMKM2A3CGNOFPGK3CSW7RIE4M3PWYC2P2E","assetId":254121594,"forceShouldClose":false,"useForceShouldCloseOrNot":true,"txnNum":0}}
```



* execute\_partial -> case where the order has partially filled, there's still some amount left in the orderbooks
* escrowAddr -> escrow wallet Now interesting bit is mapping all buys and sells... Since every partial buy/sell is to be counted Here's a escrow as a case study:
* https://algoexplorer.io/address/ZH7QQCIQAADHYDOUAH77KMJDKDQ6GKNTHG2D64JV3V6VN66XV57EJU2WYQ The very last set of txns are all: execute\_full as in the final sell/buy that filled/completed the order
* Order placement/open: https://algoexplorer.io/tx/group/xI4UCNnnyZCaVlZ8HtaUjC2Jdy6ubfrN9hNE6xcjx%2FI%3D
* Partial fill: https://algoexplorer.io/tx/group/pqUYHvEIQj6pWbEZWQaCG192kDuBiE6gaCrGwIXvDyg%3D
* Execute Full/Close/Filled: https://algoexplorer.io/tx/TDQCSGQAAHA3GQED3ZJ5ELFIG53XPZJKW2F2BTRWOMFPPYBZBF2Q
