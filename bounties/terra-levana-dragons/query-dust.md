---
description: Credits - brian_#3619
---

# QUERY - Dust

```
select *
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
```
