---
description: Credits - brian_#3619
---

# QUERY - Meteors

```
select  *
  from  terra.msgs 
  where msg_value:contract::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' 
  and   msg_value:sender::string = 'terra1v7v2nqs7flrpqqam7l5ulvnva8ly8j653sw4n3'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
```
