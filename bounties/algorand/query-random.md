---
description: 'Credits: TheLaughingMan#3062'
---

# QUERY - Random

```
SELECT    
        date_trunc('hour', block_timestamp) as ttime,
        MAX(tx_group_id) as hour_tx_group,
        COUNT(tx_group_id) as total_txns
from algorand.transactions
WHERE
    (block_timestamp>='2022-02-09' AND block_timestamp<'2022-02-10')
    AND tx_message:txn:note like '%InR4bk51bSI%'
GROUP BY ttime
```

```
SELECT    REGEXP_SUBSTR( TRY_BASE64_DECODE_STRING(TX_MESSAGE:txn:note), '.* ":(.*)', 1, 1, 'e', 1) as substr_note,
          PARSE_JSON(SUBSTRING( substr_note, 0, LEN(substr_note) -1 )) as json_note,
          json_note:escrowAddr as escrow_wallet
from algorand.transactions
WHERE 
    tx_group_id = 'zqzH8XZxoaVXWmkHBMQw7NeLtYL7+nMSdk9euNbF+dE='
```

```
CASE tx_message:txn:apid
          WHEN 354073834 then 'ASA'
          WHEN 354073718 then 'ALGO'
```
