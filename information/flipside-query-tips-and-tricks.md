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

### Handle Null Values (todo)

```
Select * from ...
```

### RegExp\_String (todo)

```
Select * from ...
```
