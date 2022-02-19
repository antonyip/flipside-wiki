---
description: 'Credits: TheLaughingMan#3062'
---

# TUTORIAL - ASA Buy/Sell

![](<../../.gitbook/assets/image (1) (1) (1) (1).png>)

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

![](<../../.gitbook/assets/image (1) (1) (1).png>)
