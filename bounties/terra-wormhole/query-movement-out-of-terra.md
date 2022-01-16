# QUERY - Movement Out of Terra

```
CASE WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 1 THEN 'Solana'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 2 THEN 'Ethereum'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 3 THEN 'Terra'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 4 THEN 'BSC'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 5 THEN 'Polygon'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 6 THEN 'Avax'
 WHEN msg_value:execute_msg:initiate_transfer:recipient_chain = 7 THEN 'Oasis'
```
