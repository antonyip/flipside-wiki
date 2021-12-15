---
description: Credits - Orion (9R)#3332
---

# QUERY - RaiseTheCaps

Caps are controlled by mimir values.

```
SELECT 
  block_id, 
  block_timestamp, 
  value 
FROM thorchain.set_mimir_events 
WHERE upper(key) = 'MAXIMUMLIQUIDITYRUNE'
ORDER BY block_id   
```
