---
description: Credits - brian_#3619
---

# QUERY - Eggs

```
select *
  from  terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and   msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
```
