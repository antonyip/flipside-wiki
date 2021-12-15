# Query - Daily Active Validator Count

```
WITH dates as (select distinct date(block_timestamp) as dates from terra.msgs where block_timestamp >= '2021-04-11T00:00:00Z' )
, counts_additions as (
select 
  date(block_timestamp) as ddate, 
  count(current_status) as additions
  from thorchain.update_node_account_status_events
where CURRENT_STATUS = 'Active'
group by ddate
order by ddate
)
, counts_subtractions as (
select 
  date(block_timestamp) as ddate, 
  count(former_status) as subtractions
  from thorchain.update_node_account_status_events
where FORMER_STATUS = 'Active'
group by ddate
order by ddate
)
, combi as (
  select 
  a.ddate as ddate,
  additions,
  -subtractions as subtractions
  from counts_additions a ,counts_subtractions s
  where a.ddate = s.ddate
)

select 
  dates,
  sum(additions + subtractions) over (order by dates) as active_validators,
  additions,
  subtractions
  from dates
LEFT JOIN combi on dates = ddate
order by dates
```
