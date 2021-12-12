# Terra - Wormhole

### Wormhole

DECODE - Which Chain the TX comes from.

```
SELECT 
 block_timestamp, msg_value:sender::string as sender, 
 HEX_ENCODE(BASE64_DECODE_BINARY(msg_value:execute_msg:submit_vaa:data::string)) as vaa_data,
 CASE 
   WHEN vaa_data ILIKE '%ec7372995d5cc8732397fb0ad35c0121e0eaa90d26f828a534cab54391b3a4f5%' THEN 'Solana'
   WHEN vaa_data ILIKE '%0000000000000000000000003ee18b2214aff97000d974cf647e7c347e8fa585%' THEN 'Ethereum'
   WHEN vaa_data ILIKE '%000000000000000000000000b6f6d86a8f9879a9c87f643768d9efc38c1da6e7%' THEN 'BSC'
   WHEN vaa_data ILIKE '%0000000000000000000000005a58505a96d1dbf8df91cb21b54419fc36e93fde%' THEN 'Polygon'
   ELSE 'Unknown Chain'
 END as emitter_chain
FROM terra.msgs
WHERE tx_id = '05A1DF7D5B88490E0652A47EE069092A3123FCF0B9F5EAF4D89FFF5C2C6C3ED4' -- sol test tx
```
