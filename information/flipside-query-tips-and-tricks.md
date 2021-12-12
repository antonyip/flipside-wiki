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

### Handle Null Values (todo)

```
Select * from ...
```

### RegExp\_String (todo)

```
Select * from ...
```
