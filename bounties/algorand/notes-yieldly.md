---
description: 'Credits: TheLaughingMan#3062'
---

# NOTES - Yieldly

If you read the docs, all of these transactions are in particular sequence in the tx\_group.

The order of what's where in the tx\_group changes based on what assets are being swapped ( ASA vs ALGO )

But the majority of the non-unique stuff stays the same. ( Fee / app call txns in the group )

And, to arrange into the order within the tx\_group\_id, you have to rely on the 'intra' field. Maybe invoke something like this:

```
SELECT row_number() OVER (PARTITION by TX_GROUP_ID ORDER BY intra) as order_num
```

This gives you tx ordering starting from 1 to N, 1st almost always is the fee, 2nd the app\_call txn

You can later build something like ( for swaps ):

```
filter_buys as ( 
    SELECT
        COUNT(tx_id) as totals,
          MAX(CASE WHEN order_num=1 THEN sender ELSE NULL END) as wallet,
          MAX(CASE WHEN order_num=2 THEN sender ELSE NULL END) as app_call_sender,
          MAX(CASE WHEN order_num=4 THEN sender ELSE NULL END) as final_sender,

          MAX(CASE WHEN order_num=3 THEN tx_message:txn:amt/1e6 ELSE NULL END) as algo_amount,
          MAX(CASE WHEN order_num=4 THEN tx_message:txn:xaid ELSE NULL END) as token_id,
          MAX(CASE WHEN order_num=4 THEN tx_message:txn:aamt ELSE NULL END) as token_amount,
        tx_group_id
    from base
    GROUP BY tx_group_id
),

filter_sells as ( 
    SELECT
        COUNT(tx_id) as totals,
          MAX(CASE WHEN order_num=1 THEN sender ELSE NULL END) as wallet,
          MAX(CASE WHEN order_num=2 THEN sender ELSE NULL END) as app_call_sender,
          MAX(CASE WHEN order_num=4 THEN sender ELSE NULL END) as final_sender,

          MAX(CASE WHEN order_num=4 THEN tx_message:txn:amt/1e6 ELSE NULL END) as algo_amount,
          MAX(CASE WHEN order_num=3 THEN tx_message:txn:xaid ELSE NULL END) as token_id,
          MAX(CASE WHEN order_num=3 THEN tx_message:txn:aamt ELSE NULL END) as token_amount,
        tx_group_id
    from base
    GROUP BY tx_group_id
),
```

Depending on whether it's a ALGO->ASA or ASA->ALGO swap, the txns and their inputs change at position 3/4.

Something similar can be done for the liquidity events, add/remove ( mint/burn of the LP token too! )

That's where the tx\_id totals come into picture, swaps involve 4 txns, LP crap 5

Gets a bit more complicated if it's going to be a ASA->ASA swap but blerrghhh

Helps to have checks for totals and algo\_amount being NULL to avoid weird/invalid cases
