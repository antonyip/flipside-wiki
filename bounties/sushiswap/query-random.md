# Query - Random

```
-- settlement contracts
Select * from ethereum.events_emitted
where lower(event_name) like '%orderfill%'
 and lower(contract_name) = 'sushiswap: settlement' 
limit 200
```

```
Select distinct contract_name,contract_address,event_inputs,tx_to_label,
  event_name
  from ethereum.events_emitted
where lower(event_name) like '%limitorder%'
  group by 1,2,3,4,5,6
  limit 200
```
