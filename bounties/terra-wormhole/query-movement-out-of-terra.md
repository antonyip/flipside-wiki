---
description: 'Credits: Pinehearst'
---

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

### Updated IBC Query - Sam

Sample Tx: 6D3433D359E83BFCD66A45752D4774F16A8191F14451C2B73F2F0AD3879CBC32

```
select 
block_timestamp, 
event_attributes:packet_data:sender as senders,
 case
when event_attributes:packet_src_channel = 'channel-1' then 'Osmosis'
when event_attributes:packet_src_channel = 'channel-16' then 'Secret'
when event_attributes:packet_src_channel = 'channel-17' then 'Injective'
when event_attributes:packet_src_channel = 'channel-19' then 'Axelar'
when event_attributes:packet_src_channel = 'channel-20' then 'Juno'
when event_attributes:packet_src_channel = 'channel-24' then 'Kava'
when event_attributes:packet_src_channel = 'channel-26' then 'Umee'
when event_attributes:packet_src_channel = 'channel-27' then 'Omniflix'
when event_attributes:packet_src_channel in ('channel-31', 'channel-7') then 'Sifchain'
when event_attributes:packet_src_channel = 'channel-38' then 'Gravity Bridge'
when event_attributes:packet_src_channel in ('channel-41', 'channel-2') then 'Cosmos'
when event_attributes:packet_src_channel in ('channel-43', 'channel-40') then 'Orai'
when event_attributes:packet_src_channel = 'channel-45' then 'Rizon'
when event_attributes:packet_src_channel = 'channel-49' then 'Swth'
when event_attributes:packet_src_channel = 'channel-49' then 'Crescent'
ELSE 'Unlabeled' END AS destination_chain,

event_attributes:packet_data:amount  / 1e6 as ust_amount

  from terra.msg_events
  where event_type = 'send_packet'
  and destination_chain is not null
  and block_timestamp >= '2022-01-01'
  and event_attributes:packet_data:denom = 'uusd'
```
