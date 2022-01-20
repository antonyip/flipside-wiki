---
description: 'Credits: Pinehearst#1947'
---

# Query - Movement Into Terra



```
WITH WH_IN AS (  -- Receiving WH Assets 
SELECT
  date(block_timestamp) as date,
  tx_id,
  event_attributes:"recipient" as recipient,
  event_attributes:"contract" as token,
  event_attributes:"0_amount" as token_amount -- unprocessed
FROM terra.msg_events --WHERE -- tx_id = '05A1DF7D5B88490E0652A47EE069092A3123FCF0B9F5EAF4D89FFF5C2C6C3ED4' -- sol test tx
  WHERE event_attributes:"0_contract_address" = 'terra10nmmwe8r3g99a9newtqa7a75xfgs2e8z87r2sf' -- Wormhole Wrapped Registry
  AND event_attributes:"0_action" = 'complete_transfer_wrapped'
  AND event_type ='from_contract'
  AND tx_status = 'SUCCEEDED'
  AND block_timestamp > '2021-10-01'
UNION ALL 
SELECT -- REceiving Native Terra Tokens from Wormhole
  date(block_timestamp) as date,
  tx_id,
  event_attributes:recipient as recipient,
  event_attributes:denom as denom,
  event_attributes:amount as amount -- unprocessed
  FROM terra.msg_events
  WHERE event_type = 'from_contract'-- AFE75F3E33C16C2693437EC0855D2867927D07113FB4E0F5F7E87E64D453AFE8
    AND event_attributes:action = 'complete_transfer_terra_native'
    AND tx_status = 'SUCCEEDED'
    AND block_timestamp > '2021-10-01'
```
