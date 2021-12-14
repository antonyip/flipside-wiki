# Terra - Levana Dragons

### Overview

{% embed url="https://eastern-cement-397.notion.site/Levana-Meteor-Shower-b51d1513cfee449692992ca41f3e880d" %}

## Bounty page

{% embed url="https://www.notion.so/Flipside-Bounties-for-Levana-Protocol-ceafc48bf45b449e8d0b8c9423c0fb57" %}

## Contract Addresses (To be fixed)

Who owns nfts on terra, how many and what \[6:16 PM] Ownership of eggs, dust and meteors \[6:16 PM] i also need levana daily trade volume on knowhwere and randomearth

\---randomearth buy meteor msg\_value:execute\_msg:execute\_order:order:order:maker\_asset:info:nft:contract\_addr::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'

Dust buy? ---terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7

\--egg terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg

\--- Meteor Buy shower msg\_value:to\_address = 'terra1dax9mddsycvzkc429wwy494vhzhggw3d5594rt'

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
