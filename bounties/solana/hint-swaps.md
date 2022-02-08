# HINT - Swaps

Swaps are in the event\_type transfer, there is no reason to do it DEX by DEX. That's the super long way to do it. There is a pattern in the postTokenBalances field that will allow you to identify if the transfer is a swap or not.

Basically, the postTokenBalances has to have at least two entries and a certain field in the first and last entry of this array shouldn't match

A majority of Solana transfers are not swaps, there are 3.6 million swaps in our data since Jan. 28th.

Also adding extra guidance: There is a way to do it by looking at postTokenBalances.

&#x20;Basically postTokenBalances only appears for in the Solana events table with event\_type = 'transfer' in two scenarios.

&#x20;One is a swap and the other is when a token that isn't Solana is being transferred (ex. a transfer of ORCA or KIN between wallets).

In a swap, the field "mint" will be different in different indices of the postTokenBalance array.
