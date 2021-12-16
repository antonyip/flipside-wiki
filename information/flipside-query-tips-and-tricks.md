# Flipside Query Tips and Tricks

### Dates

```
select date_trunc('month', block_timestamp) from from terra.daily_balances
```

### Sum of Previous Fields Daily

```
WITH DAILY_BORROW as (
  select 
  date(block_timestamp) as ddate,
  sum(amount_usd) as daily_borrow
  from anchor.borrows
where block_timestamp > CURRENT_DATE - 365
group by ddate
), DAILY_REPAY as (
select 
  date(block_timestamp) as ddate,
  sum(amount_usd) as daily_repay
  from anchor.repay
where block_timestamp > CURRENT_DATE - 365
group by ddate
)

select 
  b.ddate,
  daily_borrow,
  -daily_repay,
  sum(daily_borrow - daily_repay) over (order by b.ddate) as net_borrow
  from DAILY_BORROW b, DAILY_REPAY r
where b.ddate = r.ddate
```

### Selecting Values with numbers in them

```
WITH GENESIS_AIRDROP_CLAIM AS (SELECT  EVENT_ATTRIBUTES:"to"::string as ADDRESS,  
SUM(EVENT_ATTRIBUTES:"0_amount"/1e6) AS AMOUNT from terra.msg_events
WHERE EVENT_ATTRIBUTES:"0_contract_address" = 'terra1kalp2knjm4cs3f59ukr4hdhuuncp648eqrgshw'
AND EVENT_ATTRIBUTES:"0_action" = 'claim'
AND BLOCK_TIMESTAMP < '2021-01-01T01:06:21Z'
GROUP BY ADDRESS)
```

### Handle Null Values

```
select 
delegator_address,
nvl(label, 'unknown_validator') as validator_name,
operator_address,
vp_address
from terra.labels
```

### regexp\_substr Example

```
select 
  sum(from_amount_usd) as from_usd,
  sum(to_amount_usd) as to_usd,
  nvl(regexp_substr(from_asset,'(.*?)-',1,1,'s',1), from_asset) as from_asset,  
  nvl(regexp_substr(to_asset,'(.*?)-',1,1,'s',1), to_asset) as to_asset
  from thorchain.swaps
  where block_timestamp > CURRENT_DATE - 30
group by from_asset, to_asset

```

Flatten terra.msg\_events

```
select 
  tx_id,
  block_timestamp,
  event_index,
  msg_index,
  key,
  value,
  split(key, '_')[0] as number,
  split(key, '_')[1]::string as type
from terra.msg_events,
  lateral flatten( input => event_attributes )
where tx_id = '1DD81ADE6481C2AC3A07D8CAF07A5C3527580A8755107B191007A3F2D67C231D'
```
