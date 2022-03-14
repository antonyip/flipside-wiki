# Flipside Query Tips and Tricks

### Dates

```
select date_trunc('month', block_timestamp) from from terra.daily_balances
```

```
Hey! I'd like to delete only 2 days from a query where I take a full month.
SELECT days, amount 
FROM table.example 
WHERE days > '2021-10-01' 
AND days < '2021-11-01'

I wouldn't wanted to get 2021-11-14 and 2021-11-15  (Just an example)
AND days NOT IN ( '2021-11-14', ' 2021-11-15')
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

### Flatten terra.msg\_events

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

### dealing with JSON THINGS

```
FROM BRIAN_
When querying event_attributes in terra.msg_events or msg_value in terra.msgs, you want to use this viewer (if you're not well-versed in parsing the json otherwise).

http://jsonviewer.stack.hu/

This is incorrect:
msg_value:execute_msg:mint:extension:owner


If you look in the jsonviewer, you'll see that it should be:
msg_value:execute_msg:mint:owner


Then you can type ::string for the string
msg_value:execute_msg:mint:owner::string


Copy and paste this json into the viewer and you'll be able to see this image:
{ "@type": "/terra.wasm.v1beta1.MsgExecuteContract", "coins": [], "contract": "terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v", "execute_msg": { "mint": { "extension": { "attributes": [ { "trait_type": "rarity", "value": "Rare" }, { "trait_type": "rank", "value": "10614" }, { "trait_type": "shower", "value": "40" }, { "trait_type": "distance", "value": "890 kiloparsecs" }, { "trait_type": "crystal1", "value": "Red" }, { "trait_type": "crystal2", "value": "Yellow" }, { "trait_type": "crystal3", "value": "" }, { "trait_type": "weight", "value": "2.7kg" }, { "trait_type": "origin", "value": "Southern hemisphere subterranean caves" }, { "trait_type": "essence", "value": "Electricty" } ], "description": "Evolutionary Rare Meteor NFT, stage 1 of the Levana Dragons adventure.", "image": "ipfs://QmXti2f5NJMVyNDfhZYyxaDJvybGk7V98t245fP7KtRMxK", "name": "Levana Dragons: Rare Meteor #15514" }, "owner": "terra1flkgmdr2za7fv07cm6s62jp4t70etjw4x0zynu", "token_id": "15514" } }, "sender": "terra1v7v2nqs7flrpqqam7l5ulvnva8ly8j653sw4n3" }


```

### Share Plots quickly with others

![](../../.gitbook/assets/quickshare.png)

### Smooth Charts

```
-- Credits: AD#5391
-- Table containing all days over the last 40 days
with dates as (
 select
  -- first argument is unit of time to add, second is amount to increment, third is starting date
  dateadd(day, '-' || row_number() over (order by null),  current_date() + 1) as date
 from table (generator(rowcount => 40))
),

-- Prices over the last 30 days (artifically create missing data for this example)
prices as (
  select
      date_trunc('day', block_timestamp) as date,
      avg(price_usd) as price
  from terra.oracle_prices
  where
      symbol = 'LUNA'
    and date >= current_date() - 30
  group by date
  order by date desc
)

select 
  dates.date,
  coalesce(prices.price, 0) as price
from prices
full outer join dates on prices.date = dates.date
order by date desc
```

### Joining Addresses To Labels

![](<../../.gitbook/assets/image (2) (1) (1).png>)

### Lag Example

```
  SELECT
  date(hour) as date,
  symbol,
  token_address,
  avg(price) as daily_avg_usd,
  median(price) as daily_median_usd,
  lag(daily_avg_usd) ignore nulls over(partition by symbol ORDER BY date ASC) as price_prev,
  ((daily_avg_usd - price_prev)/daily_avg_usd)*100 as delta_percent
FROM ethereum.token_prices_hourly_v2
 WHERE symbol IN ('WETH', 'WBNB', 'SOL', 'LUNA', 'AVAX', 'MATIC', 'ALGO', 'FTM', 'ATOM') 
    AND token_address !='0x2730d6fdc86c95a74253beffaa8306b40fedecbb' -- wrong UNI
    AND token_address !='0xe6877ea9c28fbdec631ffbc087956d0023a76bf2' -- wrong UNI
    AND token_address !='0x1f54638b7737193ffd86c19ec51907a7c41755d8' -- wrong SOL
--   AND DATEDIFF(day, hour, GETDATE()) between 0 and 60
GROUP BY 1,2,3
```

### PIVOT (Rows to Columns): thanks sam#0575

![](<../../.gitbook/assets/image (2) (1).png>)

### UNPIVOT (Columns to Rows): thanks sam#0575

![](<../../.gitbook/assets/image (5).png>)

### Generate Dates

```
-- refer to smooth charts instead, this has some problem with joins
with index_table as (
select seq4() as count
  from table(generator(rowcount => 365)) t
)

select 
dateadd('hour', count, date('2022-01-01')) as day_date
from index_table
```

### Ranking Rows or Generating Row Numbers

```
row_number() over ( order by <sum_count> desc ) as rank
```

### Lag Example

```
SELECT
  date_trunc('day',block_timestamp) as day_date,
  sum(deposit_amount) as deposit_ust_daily,
  sum(mint_amount) as mint_daily,
  deposit_ust_daily/mint_daily as est_aust_price,
  LAG(est_aust_Price) ignore nulls over (order by day_date) as yesterday_price,
  (est_aust_price-yesterday_price)/yesterday_price * 365 as interestRate
FROM anchor.deposits
  where block_timestamp > current_date - 30
GROUP BY 1 
ORDER BY 1
```
