---
description: 'Credits: TheLaughingMan#3062'
---

# NOTES - Old Txs



App ID for swaps: 552635992 Group TX ID for Example Swap: f+FakJtDw9d4mV5k4NkCs5OFgJeWo1d5f03aBQ7+1t4=

Documentation on Tinyman Swaps: https://docs.tinyman.org/integration/transactions/swap

Example Transactions:

TX\_GROUP\_ID Providing liquidity Pool: svdZVwSV5NYSs4CKKl//25mCiKkJsHmGjwDXe0LsABk=

TX\_GROUP\_ID Removing liquidity from a Pool: /MihgjV0pc29vhpZArEoLdygz2O1YGmhHIAIuIJt/xE=

NFT Madlads

[https://ab2.gallery/asset/326189642](https://ab2.gallery/asset/326189642) 111.111 K algo, [https://ab2.gallery/asset/326197463](https://ab2.gallery/asset/326197463) 42.069 K algo....

Partial Sale

{% embed url="https://algoexplorer.io/tx/group/Pw5GneFk51bpXmyXCeSFyPb8Ys3ZVEYiR22u%2FP1KVOI%3D" %}
https://algoexplorer.io/tx/group/Pw5GneFk51bpXmyXCeSFyPb8Ys3ZVEYiR22u%2FP1KVOI%3D
{% endembed %}

![](<../../.gitbook/assets/image (6).png>)

{% embed url="https://algoexplorer.io" %}

Extract number from decoded strings

regexp\_replace(note, '^af/gov1:j{"com":|}$|,.\*') as commit\_amount

```
-- GET TINYMMAN groups
with tinyman_txns as (
    SELECT tx_group_id, sender
    from algorand.application_call_transaction
      WHERE
          app_id =  '552635992'
          AND block_id >= '18718205'
),
-- CHECK each TX_GROUP and how many txns it has
all_groups as (
    SELECT   COUNT(DISTINCT tx_id) as totals,
             tx_group_id
    from algorand.transactions
    WHERE
        tx_group_id IN ( SELECT tx_group_id from tinyman_txns)
    GROUP BY tx_group_id
),

SELECT * from all_groups
WHERE
    totals = 4 --SWAPs only have 4 txns in them
LIMIT 10
```

![](<../../.gitbook/assets/image (2).png>)

