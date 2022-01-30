# Query - Liqudidations

```
select 
  count(tx_id) as nb_liquidation_bids,
  date_trunc('hour', block_timestamp)  as time
  from terra.msgs
where tx_status = 'SUCCEEDED'
and block_timestamp > '2022-01-10'
AND msg_value:execute_msg:activate_bids IS NOT NULL
AND msg_value:contract = 'terra1e25zllgag7j9xsun3me4stnye2pcg66234je3u' -- This Anchor contract is for all bLuna and bETH liquidation bids. 
group by 2
```
