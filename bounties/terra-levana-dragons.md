# Terra - Levana Dragons

### Token

{% embed url="https://finder.extraterrestrial.money/mainnet/address/terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v" %}
terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v
{% endembed %}

### Something from Massnomis

```
with LVN_Meteor as (
select 
 date_trunc('day',block_timestamp) as LVN_day,
  count(distinct(tx_id)) as LVN_tx
  from terra.msgs

  where tx_status = 'SUCCEEDED'
and msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
group by 1
order by 1 desc
)
,

not_meteor as
  (select 
 date_trunc('day',block_timestamp) as n_LVN_day,
  count(distinct(tx_id)) as not_LVN_tx
  from terra.msgs

  where tx_status = 'SUCCEEDED'
and msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string <> 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
group by 1
order by 1 desc)

, lastly as (
  
select * from LVN_Meteor
left join not_meteor 
on LVN_Meteor.LVN_day = not_meteor.n_LVN_day


)

select 
LVN_DAY,
LVN_TX as Meteor_tx, 
NOT_LVN_TX as non_metor_tx,
(LVN_TX+NOT_LVN_TX) as total_tx,
(LVN_TX/total_tx) * 100 as meteor_secondary_share_pct 
from lastly
order by 1 desc
```
