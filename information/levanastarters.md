SOME QUERIES AND ARTICLES

https://anton-yip.gitbook.io/flipside-wiki/bounties/terra-random-earth/query-sales

DEGEN SCORE AND METEORS
https://rpubs.com/Zook/Levana2

nft-sales-volume-on-terras-randomearth-and-knowwhere
https://www.techdreams.org/crypto-currency/nft-sales-volume-on-terras-randomearth-and-knowwhere/11668-20211214

participants-and-ust-deposits-by-hour-on-levana
https://www.techdreams.org/crypto-currency/participants-and-ust-deposits-by-hour-on-levana/11194-20211117

https://eastern-cement-397.notion.site/Levana-Meteor-Shower-b51d1513cfee449692992ca41f3e880d

https://app.flipsidecrypto.com/dashboard/levana-meteor-shower-participants-MtfTMc


DUST TRAITS
```
WITH 
  ancient_traits1 as (

select   block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as ancient_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as common_gem,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as weight,
         null                                                              as legendary_composition,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as ancient_composition,
         msg_value:execute_msg:mint:extension:attributes[14]:value::string as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[15]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[16]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[17]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Ancient'
  and    msg_value:execute_msg:mint:extension:attributes[13]:trait_type::string <> 'Legendary Composition'),

  ancient_traits2 as (select block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as ancient_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as common_gem,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as weight,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as legendary_composition,
         msg_value:execute_msg:mint:extension:attributes[14]:value::string as ancient_composition,
         msg_value:execute_msg:mint:extension:attributes[15]:value::string as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[16]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[17]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[18]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Ancient'
  and    msg_value:execute_msg:mint:extension:attributes[13]:trait_type::string = 'Legendary Composition'
  ),

  rare_traits1 as (
  
  select block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         null                                                              as ancient_gem,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as common_gem,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as legendary_composition,
         null                                                              as ancient_composition,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[14]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[15]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[16]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Rare'
  and    msg_value:execute_msg:mint:extension:attributes[12]:trait_type::string = 'Legendary Composition'),

  rare_traits2 as (
  
  select block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         null                                                              as ancient_gem,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as common_gem,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
         null                                                              as legendary_composition,
         null                                                              as ancient_composition,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[14]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[15]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Rare'
  and    msg_value:execute_msg:mint:extension:attributes[12]:trait_type::string <> 'Legendary Composition'),

  common_traits1 as (
  
  select block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         null                                                              as ancient_gem,
         null                                                              as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as common_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as weight,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as legendary_composition,
         null                                                              as ancient_composition,
         null                                                              as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[14]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Common'
  and    msg_value:execute_msg:mint:extension:attributes[11]:trait_type::string = 'Legendary Composition'),

  common_traits2 as (
  
  select block_timestamp,
         block_id,
         tx_id,
         msg_value:execute_msg:mint:extension:name::string                 as name,
         msg_value:execute_msg:mint:token_id::float                        as tokenid,
         msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
         msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
         msg_value:execute_msg:mint:extension:attributes[2]:value::string  as dust_volume,
         msg_value:execute_msg:mint:extension:attributes[3]:value::string  as spirit_level,
         msg_value:execute_msg:mint:extension:attributes[4]:value::string  as origin,
         msg_value:execute_msg:mint:extension:attributes[5]:value::string  as bottling_date,
         msg_value:execute_msg:mint:extension:attributes[6]:value::string  as essence,
         msg_value:execute_msg:mint:extension:attributes[7]:value::string  as rune,
         msg_value:execute_msg:mint:extension:attributes[8]:value::string  as infusion,
         null                                                              as ancient_gem,
         null                                                              as rare_gem,
         msg_value:execute_msg:mint:extension:attributes[9]:value::string  as common_gem,
         msg_value:execute_msg:mint:extension:attributes[10]:value::string as weight,
         null                                                              as legendary_composition,
         null                                                              as ancient_composition,
         null                                                              as rare_composition,
         msg_value:execute_msg:mint:extension:attributes[11]:value::string as common_composition,
         msg_value:execute_msg:mint:extension:attributes[12]:value::string as shower,
         msg_value:execute_msg:mint:extension:attributes[13]:value::string as meteor_id
  from   terra.msgs 
  where  msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and    msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and    msg_value:execute_msg:mint is not null
  and    tx_status = 'SUCCEEDED'
  and    rarity = 'Common'
  and    msg_value:execute_msg:mint:extension:attributes[11]:trait_type::string <> 'Legendary Composition'),
  
combine AS (

        select * from ancient_traits1
        UNION ALL
        select * from ancient_traits2
        UNION ALL
        select * from rare_traits1
        UNION ALL
        select * from rare_traits2
        UNION ALL
        select * from common_traits1
        UNION ALL
        select * from common_traits2
        
        )
  
select * from combine order by tokenid
```

EGG TRAITS
```
WITH legendary_traits AS (

 select block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                 as name,
        msg_value:execute_msg:mint:token_id::float                        as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string  as origin,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string  as cracking_date,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string  as essence,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string  as rune,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string  as infusion,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string  as affecting_moon,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string  as lucky_number,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string  as constellation,
        msg_value:execute_msg:mint:extension:attributes[10]:value::string as temperature,
        msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[12]:value::string as family,
        msg_value:execute_msg:mint:extension:attributes[13]:value::string as genus,
        msg_value:execute_msg:mint:extension:attributes[18]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[19]:value::string as meteor_id,
        msg_value:execute_msg:mint:extension:attributes[14]:value::string as legendary_composition,
        msg_value:execute_msg:mint:extension:attributes[15]:value::string as ancient_composition,
        msg_value:execute_msg:mint:extension:attributes[16]:value::string as rare_composition,
        msg_value:execute_msg:mint:extension:attributes[17]:value::string as common_composition
  from  terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and   msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
  and   rarity = 'Legendary'),
  
  ancient_traits as (
  
 select block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                 as name,
        msg_value:execute_msg:mint:token_id::float                        as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string  as origin,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string  as cracking_date,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string  as essence,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string  as rune,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string  as infusion,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string  as affecting_moon,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string  as lucky_number,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string  as constellation,
        msg_value:execute_msg:mint:extension:attributes[10]:value::string as temperature,
        msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[12]:value::string as family,
        msg_value:execute_msg:mint:extension:attributes[13]:value::string as genus,
        msg_value:execute_msg:mint:extension:attributes[17]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[18]:value::string as meteor_id,
        null                                                              as legendary_composition,
        msg_value:execute_msg:mint:extension:attributes[14]:value::string as ancient_composition,
        msg_value:execute_msg:mint:extension:attributes[15]:value::string as rare_composition,
        msg_value:execute_msg:mint:extension:attributes[16]:value::string as common_composition
  from  terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and   msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
  and   rarity = 'Ancient'),
  
  rare_traits as (
  
 select block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                 as name,
        msg_value:execute_msg:mint:token_id::float                        as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string  as origin,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string  as cracking_date,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string  as essence,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string  as rune,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string  as infusion,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string  as affecting_moon,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string  as lucky_number,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string  as constellation,
        msg_value:execute_msg:mint:extension:attributes[10]:value::string as temperature,
        msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[12]:value::string as family,
        msg_value:execute_msg:mint:extension:attributes[13]:value::string as genus,
        msg_value:execute_msg:mint:extension:attributes[16]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[17]:value::string as meteor_id,
        null                                                              as legendary_composition,
        null                                                              as ancient_composition,
        msg_value:execute_msg:mint:extension:attributes[14]:value::string as rare_composition,
        msg_value:execute_msg:mint:extension:attributes[15]:value::string as common_composition
  from  terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and   msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
  and   rarity = 'Rare'),
  
  common_traits as (
  
 select block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                 as name,
        msg_value:execute_msg:mint:token_id::float                        as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string  as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string  as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string  as origin,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string  as cracking_date,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string  as essence,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string  as rune,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string  as infusion,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string  as affecting_moon,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string  as lucky_number,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string  as constellation,
        msg_value:execute_msg:mint:extension:attributes[10]:value::string as temperature,
        msg_value:execute_msg:mint:extension:attributes[11]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[12]:value::string as family,
        msg_value:execute_msg:mint:extension:attributes[13]:value::string as genus,
        msg_value:execute_msg:mint:extension:attributes[15]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[16]:value::string as meteor_id,
        null                                                              as legendary_composition,
        null                                                              as ancient_composition,
        null                                                              as rare_composition,
        msg_value:execute_msg:mint:extension:attributes[14]:value::string as common_composition
  from  terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and   msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED'
  and   rarity = 'Common'),
  
combine AS (

      select * from legendary_traits
      UNION ALL
      select * from ancient_traits
      UNION ALL
      select * from rare_traits
      UNION ALL
      select * from common_traits
      
      )

select * from combine order by tokenid
```

METEOR TRAITS
```
WITH meteor_traits AS (

select  block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                as name,
        msg_value:execute_msg:mint:token_id::float                       as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string as distance,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string as crystal1,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string as crystal2,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string as crystal3,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string as origin,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string as essence
  from  terra.msgs 
  where msg_value:contract::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' 
  and   msg_value:sender::string = 'terra1v7v2nqs7flrpqqam7l5ulvnva8ly8j653sw4n3'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED')
  
select * from meteor_traits order by tokenid 



NFT OWNERS, KW+RA setttle
with transfer_nfts AS ( 
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		event_attributes:token_id::string as tokenid,
  		event_attributes:recipient::string as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	action = 'transfer_nft'
  and (event_attributes:contract_address::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'))
  ,
  
   orders_nfts AS (
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		nvl(event_attributes:order:order:maker_asset:info:nft:token_id::string,
  			event_attributes:order:order:taker_asset:info:nft:token_id::string) as tokenid,
  		nvl(event_attributes:recipient::string,event_attributes:sender::string) as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	(action = 'execute_orders')
  and (event_attributes:contract_address::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'))
,
  
  KW_sendnft AS (
                select  block_timestamp,
                  		tx_id,
  						'string' AS action,
                  		msg_value:execute_msg:send_nft:token_id::string AS tokenid,
                  		msg_value:sender::string AS owner
                  from terra.msgs 
                  where msg_value:contract::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v'
                	and	msg_value:execute_msg:send_nft:contract::string = 'terra12v8vrgntasf37xpj282szqpdyad7dgmkgnq60j'
                	and	tx_status = 'SUCCEEDED'
  ),
  
    KW_settle AS (
                select  block_timestamp,
  						tx_id,
  						'string' AS action,
  						event_attributes:token_id::string AS tokenid,
  						event_attributes:recipient::string AS owner
                  from terra.msg_events
                 where event_type = 'from_contract'
  					and event_attributes:"0_action"::string = 'settle'
  					and event_attributes:"1_contract_address"::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v')
  ,
  
  mintowners AS (select  block_timestamp,
  		tx_id,
  		'string' AS action,
  		msg_value:execute_msg:mint:token_id::string AS tokenID,
  		msg_value:execute_msg:mint:owner::string AS owner
  from terra.msgs 
  where msg_value:contract::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' 
  and	msg_value:sender::string = 'terra1v7v2nqs7flrpqqam7l5ulvnva8ly8j653sw4n3'
  and	msg_value:execute_msg:mint is not null)
  ,
  
  qmain AS (
select * from transfer_nfts
  UNION
select * from orders_nfts
  UNION
select * from KW_sendnft
  UNION
select * from KW_settle
  UNION
select * from mintowners
  )
  ,
  latestowners as (
  select block_timestamp,
  		 tx_id,
  		 lower(owner) AS owner,
  		 tokenid
  from qmain
where block_timestamp = (select max(a.block_timestamp)
  							from qmain a
  							where a.tokenid = qmain.tokenid))
,
  transfer_nfts1 AS (
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		event_attributes:token_id::string as tokenid,
  		event_attributes:recipient::string as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	action = 'transfer_nft'
  and (event_attributes:contract_address::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'))
  ,
  
   orders_nfts1 AS (
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		nvl(event_attributes:order:order:maker_asset:info:nft:token_id::string,
  			event_attributes:order:order:taker_asset:info:nft:token_id::string) as tokenid,
  		nvl(event_attributes:recipient::string,event_attributes:sender::string) as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	(action = 'execute_orders')
  and (event_attributes:contract_address::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'))
,
  
  KW_sendnft1 AS (
                select  block_timestamp,
                  		tx_id,
  						'string' AS action,
                  		msg_value:execute_msg:send_nft:token_id::string AS tokenid,
                  		msg_value:sender::string AS owner
                  from terra.msgs 
                  where msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7'
                	and	msg_value:execute_msg:send_nft:contract::string = 'terra12v8vrgntasf37xpj282szqpdyad7dgmkgnq60j'
                	and	tx_status = 'SUCCEEDED'
  ),
  
    KW_settle1 AS (
                select  block_timestamp,
  						tx_id,
  						'string' AS action,
  						event_attributes:token_id::string AS tokenid,
  						event_attributes:recipient::string AS owner
                  from terra.msg_events
                 where event_type = 'from_contract'
  					and event_attributes:"0_action"::string = 'settle'
  					and event_attributes:"1_contract_address"::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7')
  ,
    mintowners1 AS (select  block_timestamp,
  		tx_id,
  		'string' AS action,
  		msg_value:execute_msg:mint:token_id::string AS tokenID,
  		msg_value:execute_msg:mint:owner::string AS owner
  from terra.msgs 
  where msg_value:contract::string = 'terra1p70x7jkqhf37qa7qm4v23g4u4g8ka4ktxudxa7' 
  and	msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and	msg_value:execute_msg:mint is not null)
,
  qmain1 AS (
select * from transfer_nfts1
  UNION
select * from orders_nfts1
  UNION
select * from KW_sendnft1
  UNION
select * from KW_settle1
  UNION
select * from mintowners1
  )
  ,
  latestowners1 as (
  select block_timestamp,
  		 tx_id,
  		 lower(owner) AS owner,
  		 tokenid
  from qmain1
where block_timestamp = (select max(a.block_timestamp)
  							from qmain1 a
  							where a.tokenid = qmain1.tokenid))
,
  transfer_nfts2 AS (
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		event_attributes:token_id::string as tokenid,
  		event_attributes:recipient::string as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	action = 'transfer_nft'
  and (event_attributes:contract_address::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'))
  ,
  
   orders_nfts2 AS (
select  block_timestamp,
  		tx_id,
  		event_attributes:action::string as action,
  		nvl(event_attributes:order:order:maker_asset:info:nft:token_id::string,
  			event_attributes:order:order:taker_asset:info:nft:token_id::string) as tokenid,
  		nvl(event_attributes:recipient::string,event_attributes:sender::string) as owner
  from terra.msg_events 
  where event_type = 'wasm'
  and	tx_status = 'SUCCEEDED'
  and	(action = 'execute_orders')
  and (event_attributes:contract_address::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'
	or	event_attributes:order:order:maker_asset:info:nft:contract_addr = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'
	or	event_attributes:order:order:taker_asset:info:nft:contract_addr = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'))
,
  
  KW_sendnft2 AS (
                select  block_timestamp,
                  		tx_id,
  						'string' AS action,
                  		msg_value:execute_msg:send_nft:token_id::string AS tokenid,
                  		msg_value:sender::string AS owner
                  from terra.msgs 
                  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg'
                	and	msg_value:execute_msg:send_nft:contract::string = 'terra12v8vrgntasf37xpj282szqpdyad7dgmkgnq60j'
                	and	tx_status = 'SUCCEEDED'
  ),
  
    KW_settle2 AS (
                select  block_timestamp,
  						tx_id,
  						'string' AS action,
  						event_attributes:token_id::string AS tokenid,
  						event_attributes:recipient::string AS owner
                  from terra.msg_events
                 where event_type = 'from_contract'
  					and event_attributes:"0_action"::string = 'settle'
  					and event_attributes:"1_contract_address"::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg')
  ,
    mintowners2 AS (select  block_timestamp,
  		tx_id,
  		'string' AS action,
  		msg_value:execute_msg:mint:token_id::string AS tokenID,
  		msg_value:execute_msg:mint:owner::string AS owner
  from terra.msgs 
  where msg_value:contract::string = 'terra1k0y373yxqne22pc9g7jvnr4qclpsxtafevtrpg' 
  and	msg_value:sender::string = 'terra1awy9ychm2z2hd696kz6yeq67l30l7nxs7n762t'
  and	msg_value:execute_msg:mint is not null)
,
  qmain2 AS (
select * from transfer_nfts2
  UNION
select * from orders_nfts2
  UNION
select * from KW_sendnft2
  UNION
select * from KW_settle2
  UNION
select * from mintowners2
  )
  ,
  latestowners2 as (
  select block_timestamp,
  		 tx_id,
  		 lower(owner) AS owner,
  		 tokenid
  from qmain2
where block_timestamp = (select max(a.block_timestamp)
  							from qmain2 a
  							where a.tokenid = qmain2.tokenid))
  ,
meteorCounts AS 
  (select owner,
  		  count(tokenid) as total
  from latestowners
  group by 1
  ),
dustCounts AS 
  (select owner,
  		  count(tokenid) as total
  from latestowners1
  group by 1
  ),
eggCounts AS 
  (select owner,
  		  count(tokenid) as total
  from latestowners2
  group by 1
  )

  select nvl(nvl(o1,o2),o3) AS owner,
  		 meteors,
  		 dust,
  		 eggs
  from
  (select a.owner as o1,
	   b.owner as o2,
	   c.owner as o3,
	   nvl(a.total,0) as meteors,
	   nvl(b.total,0) AS dust,
	   nvl(c.total,0) AS eggs
from meteorcounts a
  		FULL OUTER JOIN
	 dustcounts b ON a.owner = b.owner
  		FULL OUTER JOIN
	 eggcounts c ON b.owner = c.owner)
order by 1 desc



LVN on RANDOM EARTH
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


KW
```
WITH KWsubInfo AS (
select distinct tx_id,
  				event_attributes:"1_contract_address"::string AS contract
  from terra.msg_events
  where event_attributes:"0_contract_address"::string = 'terra12v8vrgntasf37xpj282szqpdyad7dgmkgnq60j'
  and	event_attributes:"0_action"::string = 'settle'
  and	event_type = 'wasm'),

  KWsettle AS (
  select 	CASE WHEN kwsubinfo.contract = 'terra16h5elefh6y054a6tjvkw5zknlvnytw5rt842rc' THEN 'Terrasaurs'
  				 WHEN kwsubinfo.contract = 'terra1qdvv4maeur6k46ufxramp3fpx07jjz7q8dqr5q' THEN 'TerraBuds'
  				 WHEN kwsubinfo.contract = 'terra12vdepstt7f45lr8gz2flf7dnwzwlft3r22nref' THEN 'Luna Apes'
  				 WHEN kwsubinfo.contract = 'terra1azanq9ed4mgjkg2ye450kvuqamuurzgjrh0esp' THEN 'Terraverse Adventure'
  				 WHEN kwsubinfo.contract = 'terra1flwpxxfl8ldxhdgzxkwet2r37c45hutapgjwkg' THEN 'LunArt - Genesis Collection'
  				 WHEN kwsubinfo.contract = 'terra1jdt2wnfhgy4ptk6m5kxacyj0k6e8rc7e2ugulz' THEN 'TerraWhales'
  				 WHEN kwsubinfo.contract = 'terra132r4346dw7zkm0dr4rg3dlzyz38fgy3atfm69v' THEN 'Terra CosmicWaves'
  				 WHEN kwsubinfo.contract = 'terra1hj0dga445h3faxu85gm0293608qntsj3a727ck' THEN 'TerraBots'
  				 WHEN kwsubinfo.contract = 'terra12m4zhl4eqy2dkw863k3nfazxwj6vys007ur57r' THEN 'Wat Da Pug'
  				 WHEN kwsubinfo.contract = 'terra1r9x26yxkugmv5x7u9082cgapd6fusv4q0lz4fj' THEN 'Luna Kiddy Collection 1 - "Hello Moon"'
  				 WHEN kwsubinfo.contract = 'terra1luefwulrxzstxape0anahge5dwv23066xgqu0d' THEN 'Cosmic Colonist Cat'
  				 WHEN kwsubinfo.contract = 'terra13qrc9j00lk3x0rvpptzdmwtckfj64d5g6xnrv9' THEN 'SpaceLoot'
  				 WHEN kwsubinfo.contract = 'terra1ce6jq4da4u49x5mwfdun9jxz5az5uflsgqc067' THEN 'Luna Meow'
  				 WHEN kwsubinfo.contract = 'terra1fsfnnv08cgwcyfyh3p89rf44tfy4tlgnsapyda' THEN 'TNS - Terra Name Service'
  				 WHEN kwsubinfo.contract = 'terra18g7zaxuju84qzr70sslw4ahjmaehetsg0fd0y9' THEN 'Terranime Punks'
  				 WHEN kwsubinfo.contract = 'terra1zjdkagfvxxvk7grq7c5gk5h3xfvevftyrqc2vd' THEN 'Terra Cards'
  				 WHEN kwsubinfo.contract = 'terra1qlvyf2t3d5957xrljhr3t80pme2p2kdt542v0t' THEN 'Burg0rz'
  				 WHEN kwsubinfo.contract = 'terra1f5yu534nyzhpkswnx2036wv7fvscxwq42mrnw2' THEN 'Bag of Dicks'
  				 WHEN kwsubinfo.contract = 'terra1y076t8yrj0t4ag969w92ez9qfdj0c6dn7xhmkq' THEN 'Astroverse - AST1'
  				 WHEN kwsubinfo.contract = 'terra1a82yd7vfpkwqm9pv3xk54gxdtd5x36u0lvt8a8' THEN 'A Space Doodle'
  				 WHEN kwsubinfo.contract = 'terra1qn676uss04s68zqr9aq0379q2ln5w9plrz3ukc' THEN 'TerraBulls'
  				 WHEN kwsubinfo.contract = 'terra1ycp3azjymqckrdlzpp88zfyk6x09m658c2c63d' THEN 'Space Toadz'
  				 WHEN kwsubinfo.contract = 'terra1jp5fjj7rlc0erw4z3qr5zuvmg2w49pfzyhvsnk' THEN 'wagmimonkeez'
  				 WHEN kwsubinfo.contract = 'terra1kekvz7nm8ed2nd8mdny8ukuap00mg52txrnwhs' THEN 'LunaLapin'
  				 WHEN kwsubinfo.contract = 'terra1ymqxz9xu80nsp56azqpu8j94646tpkc8xxxy6w' THEN 'LunaLlamas'
  				 WHEN kwsubinfo.contract = 'terra192vcn2julwy7r2cd5prnkmnm3nxsts5sm32ygq' THEN 'xyz - contract nameless'
  				 WHEN kwsubinfo.contract = 'terra1r2q8kg6k3vyhk6x42332wprvk2e3gpdjqrqzju' THEN 'Terragods'
  				 WHEN kwsubinfo.contract = 'terra1xyu4hzx90s262tw3rl3u4563xqxtjuyu3lxp4s' THEN 'LunaKittys'
  				 WHEN kwsubinfo.contract = 'terra189qtkvsnjdladzsx5qjt24rlq8t74nhr3840xn' THEN 'Groovy Afterlife'
  				 WHEN kwsubinfo.contract = 'terra1934kn7p03ns94htl75zpzsg0n4yvw8yf2746ep' THEN 'Styllar'
  				 WHEN kwsubinfo.contract = 'terra1nckjus3laz75p6wxwvc83np7u6d9r526en8zrt' THEN 'Cosmic Adventurer - contract nameless'
  				 WHEN kwsubinfo.contract = 'terra1f89xq3qhu98v4jch4y5xcrkhl9gytrne99x74t' THEN 'Terrapins on Terra'
  				 WHEN kwsubinfo.contract = 'terra1pucsnnskzhljpex9h4zrwj93x27zk2ycw8yxsr' THEN 'The Survarian'
  				 WHEN kwsubinfo.contract = 'terra1er46zkkqu4fvjdkh6pyw3hprm68c7sdu9yt3e5' THEN 'TerraNova'
  				 WHEN kwsubinfo.contract = 'terra1whyze49j9d0672pleaflk0wfufxrh8l0at2h8q' THEN 'Terranauts'
  				 WHEN kwsubinfo.contract = 'terra1axq5cef8dnuv6hghseu5kl6909at63p28wvuhv' THEN 'TerraGems'
  				 WHEN kwsubinfo.contract = 'terra1tv5hu9d2hw4q9tn4x30870ae0e4mrttqj0fcv6' THEN 'Deviants Factions'
  				 WHEN kwsubinfo.contract = 'terra103z9cnqm8psy0nyxqtugg6m7xnwvlkqdzm4s4k' THEN 'Galactic Punks'
  				 WHEN kwsubinfo.contract = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' THEN 'Levana Dragons'
  				 WHEN kwsubinfo.contract = 'terra1lt4e5r5rhddhercgpk6v567z2yd3ucxq5n8jsh' THEN 'Red Eyed Space Toads (RESToads)'
  				 WHEN kwsubinfo.contract = 'terra12kn3xju6ha6wf9pza3g0phatwzvezratt3wrt5' THEN 'Red Eyed Space Tadpoles (Eggs)'
  				 WHEN kwsubinfo.contract = 'terra17tjd0c42c5067ykva652uj2445w976frz7yv73' THEN 'LunaLambos'
  				 WHEN kwsubinfo.contract = 'terra1trn7mhgc9e2wfkm5mhr65p3eu7a2lc526uwny2' THEN 'LunaBulls'
  				 WHEN kwsubinfo.contract = 'terra1k0rkwe4ch874eqawp5ajujtzaypnncqw7mr4hu' THEN 'Dear..lunatic'
  				 ELSE '**NO NAME**' END AS projectname,
  			kwsubinfo.contract, 
  			sum((nvl(event_attributes:"0_amount"[0]:amount::float,0) +
  			nvl(event_attributes:"1_amount"[0]:amount::float,0) + 
  			nvl(event_attributes:"2_amount"[0]:amount::float,0)) / 1e6) AS totalAmount
from terra.msg_events me, kwsubinfo
where me.tx_id = kwsubinfo.tx_id
  --and me.msg_index = 0 --for instances where place bid + settle are in the same tx. This is a 'buy now', not an auction.
  and me.event_type = 'transfer'
  group by kwsubinfo.contract)

select 	projectname AS "Project Name",
  		contract as "Contract Address",
		round(totalamount,2) as "Total Volume (LUNA)"  
  from kwsettle
order by 3 desc
```


RE
```
WITH orders AS
  (select 	msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string AS contract,
  			sum(msg_value:execute_msg:execute_order:order:order:taker_asset:amount::decimal/pow(10,6)) AS amount
  from terra.msgs 
  where msg_value:contract::string = 'terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t' 
    --and	msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string = 'terra103z9cnqm8psy0nyxqtugg6m7xnwvlkqdzm4s4k'
  and	tx_status = 'SUCCEEDED'
  and	msg_value:execute_msg:execute_order is not null
  and	contract is not null
  group by 1
  ),
Lorders AS
  (select 	msg_value:execute_msg:ledger_proxy:msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string AS contract,
  			sum(msg_value:execute_msg:ledger_proxy:msg:execute_order:order:order:taker_asset:amount::decimal/pow(10,6)) AS lamount
  from terra.msgs 
  where msg_value:contract::string = 'terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t' 
    --and	msg_value:execute_msg:ledger_proxy:msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string = 'terra103z9cnqm8psy0nyxqtugg6m7xnwvlkqdzm4s4k'
  and	tx_status = 'SUCCEEDED'
  and	msg_value:execute_msg:ledger_proxy:msg:execute_order is not null
  and	contract is not null
  group by 1
  ),
qmain AS (select NVL(orders.contract,lorders.contract) AS project, 
  NVL(amount,0) + nvl(lamount,0) AS amountt
  from orders FULL OUTER JOIN lorders 
  ON orders.contract = lorders.contract)

  select 	CASE WHEN project = 'terra16h5elefh6y054a6tjvkw5zknlvnytw5rt842rc' THEN 'Terrasaurs'
  				 WHEN project = 'terra1qdvv4maeur6k46ufxramp3fpx07jjz7q8dqr5q' THEN 'TerraBuds'
  				 WHEN project = 'terra12vdepstt7f45lr8gz2flf7dnwzwlft3r22nref' THEN 'Luna Apes'
  				 WHEN project = 'terra1azanq9ed4mgjkg2ye450kvuqamuurzgjrh0esp' THEN 'Terraverse Adventure'
  				 WHEN project = 'terra1flwpxxfl8ldxhdgzxkwet2r37c45hutapgjwkg' THEN 'LunArt - Genesis Collection'
  				 WHEN project = 'terra1jdt2wnfhgy4ptk6m5kxacyj0k6e8rc7e2ugulz' THEN 'TerraWhales'
  				 WHEN project = 'terra132r4346dw7zkm0dr4rg3dlzyz38fgy3atfm69v' THEN 'Terra CosmicWaves'
  				 WHEN project = 'terra1hj0dga445h3faxu85gm0293608qntsj3a727ck' THEN 'TerraBots'
  				 WHEN project = 'terra12m4zhl4eqy2dkw863k3nfazxwj6vys007ur57r' THEN 'Wat Da Pug'
  				 WHEN project = 'terra1r9x26yxkugmv5x7u9082cgapd6fusv4q0lz4fj' THEN 'Luna Kiddy Collection 1 - "Hello Moon"'
  				 WHEN project = 'terra1luefwulrxzstxape0anahge5dwv23066xgqu0d' THEN 'Cosmic Colonist Cat'
  				 WHEN project = 'terra13qrc9j00lk3x0rvpptzdmwtckfj64d5g6xnrv9' THEN 'SpaceLoot'
  				 WHEN project = 'terra1ce6jq4da4u49x5mwfdun9jxz5az5uflsgqc067' THEN 'Luna Meow'
  				 WHEN project = 'terra1fsfnnv08cgwcyfyh3p89rf44tfy4tlgnsapyda' THEN 'TNS - Terra Name Service'
  				 WHEN project = 'terra18g7zaxuju84qzr70sslw4ahjmaehetsg0fd0y9' THEN 'Terranime Punks'
  				 WHEN project = 'terra1zjdkagfvxxvk7grq7c5gk5h3xfvevftyrqc2vd' THEN 'Terra Cards'
  				 WHEN project = 'terra1qlvyf2t3d5957xrljhr3t80pme2p2kdt542v0t' THEN 'Burg0rz'
  				 WHEN project = 'terra1f5yu534nyzhpkswnx2036wv7fvscxwq42mrnw2' THEN 'Bag of Dicks'
  				 WHEN project = 'terra1y076t8yrj0t4ag969w92ez9qfdj0c6dn7xhmkq' THEN 'Astroverse - AST1'
  				 WHEN project = 'terra1a82yd7vfpkwqm9pv3xk54gxdtd5x36u0lvt8a8' THEN 'A Space Doodle'
  				 WHEN project = 'terra1qn676uss04s68zqr9aq0379q2ln5w9plrz3ukc' THEN 'TerraBulls'
  				 WHEN project = 'terra1ycp3azjymqckrdlzpp88zfyk6x09m658c2c63d' THEN 'Space Toadz'
  				 WHEN project = 'terra1jp5fjj7rlc0erw4z3qr5zuvmg2w49pfzyhvsnk' THEN 'wagmimonkeez'
  				 WHEN project = 'terra1kekvz7nm8ed2nd8mdny8ukuap00mg52txrnwhs' THEN 'LunaLapin'
  				 WHEN project = 'terra1ymqxz9xu80nsp56azqpu8j94646tpkc8xxxy6w' THEN 'LunaLlamas'
  				 WHEN project = 'terra192vcn2julwy7r2cd5prnkmnm3nxsts5sm32ygq' THEN 'xyz - contract nameless'
  				 WHEN project = 'terra1r2q8kg6k3vyhk6x42332wprvk2e3gpdjqrqzju' THEN 'Terragods'
  				 WHEN project = 'terra1xyu4hzx90s262tw3rl3u4563xqxtjuyu3lxp4s' THEN 'LunaKittys'
  				 WHEN project = 'terra189qtkvsnjdladzsx5qjt24rlq8t74nhr3840xn' THEN 'Groovy Afterlife'
  				 WHEN project = 'terra1934kn7p03ns94htl75zpzsg0n4yvw8yf2746ep' THEN 'Styllar'
  				 WHEN project = 'terra1nckjus3laz75p6wxwvc83np7u6d9r526en8zrt' THEN 'Cosmic Adventurer - contract nameless'
  				 WHEN project = 'terra1f89xq3qhu98v4jch4y5xcrkhl9gytrne99x74t' THEN 'Terrapins on Terra'
  				 WHEN project = 'terra1pucsnnskzhljpex9h4zrwj93x27zk2ycw8yxsr' THEN 'The Survarian'
  				 WHEN project = 'terra1er46zkkqu4fvjdkh6pyw3hprm68c7sdu9yt3e5' THEN 'TerraNova'
  				 WHEN project = 'terra1whyze49j9d0672pleaflk0wfufxrh8l0at2h8q' THEN 'Terranauts'
  				 WHEN project = 'terra1axq5cef8dnuv6hghseu5kl6909at63p28wvuhv' THEN 'TerraGems'
  				 WHEN project = 'terra1tv5hu9d2hw4q9tn4x30870ae0e4mrttqj0fcv6' THEN 'Deviants Factions'
  				 WHEN project = 'terra103z9cnqm8psy0nyxqtugg6m7xnwvlkqdzm4s4k' THEN 'Galactic Punks'
  				 WHEN project = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' THEN 'Levana Dragons'
  				 WHEN project = 'terra1lt4e5r5rhddhercgpk6v567z2yd3ucxq5n8jsh' THEN 'Red Eyed Space Toads (RESToads)'
  				 WHEN project = 'terra12kn3xju6ha6wf9pza3g0phatwzvezratt3wrt5' THEN 'Red Eyed Space Tadpoles (Eggs)'
  				 WHEN project = 'terra17tjd0c42c5067ykva652uj2445w976frz7yv73' THEN 'LunaLambos'
  				 WHEN project = 'terra1trn7mhgc9e2wfkm5mhr65p3eu7a2lc526uwny2' THEN 'LunaBulls'
  				 WHEN project = 'terra1k0rkwe4ch874eqawp5ajujtzaypnncqw7mr4hu' THEN 'Dear..lunatic'
  				 WHEN project = 'terra1h6msx3t0qj7fuhssyqc44g20qwwyz35zqel96l' THEN 'Poppin Puffins'
  				 WHEN project = 'terra1ughahl2yl5r8yc4u4j2ak8x55vjl3t0vrrd3mf' THEN 'TerraSkulls Generation 1'
  				 WHEN project = 'terra1fnv8f2202zgsnvpju7auehmygmdfj93xls8x0s' THEN 'Goochi Goochi'
  				 WHEN project = 'terra1wue25pe63g22uxy6ssjrkhnjscshdv8ztjwz5y' THEN 'NIPTerra'
  				 WHEN project = 'terra1x6wjugqwn2cwmjwrk603hmxwxcmk9n3uzzmhvh' THEN 'Planet of LunApes'
  				 WHEN project = 'terra13phhlv3qqyspr9xca858pyxfwmwsn0w7l9t25g' THEN 'Hamsters Gang'
  				 WHEN project = 'terra10cz6rlz9emt4a3sh5r5c4y4krlrad9ka5mc0qw' THEN 'Steart: Joker'
  				 WHEN project = 'terra12wc980dn3k09a4jh9we0lj5xfap58smceegfe0' THEN 'Fractals'
  				 WHEN project = 'terra13rglydrpv6mtanqp966z8ndcnrah0ejhrujt60' THEN 'Soulhunter'
  				 WHEN project = 'terra1glkeugq7ktjlcj3uaauegmsnl6947vn4vnswjq' THEN 'Veeper K-pop'
  				 WHEN project = 'terra139pqfy6armpauyqqhev7tdncs64gs26frj92y3' THEN 'Women Vs Apes'
  				 WHEN project = 'terra16y3p76t42yq7dlzuxwtcq8x2nkeutzdhqj4tgr' THEN 'TerraHare'
  				 WHEN project = 'terra1x6pypklhr9mjpjh9tqs0cp49mf0p5jwmqak92l' THEN 'Entropic Breath: Prelude'
  				 WHEN project = 'terra1xnjm9rrw9ckqmhh56lpf9pwawsfcfayjkwqqw3' THEN 'Terra Movie Club'
  				 WHEN project = 'terra19auzecsexkyzekcg5r6gvrlm4df3cardccc70w' THEN 'Tales Of Terra'
  				 WHEN project = 'terra17qxft2sshc4gel5ggd6j6hprah6dy785j9w878' THEN 'MonsTerra'
  				 WHEN project = 'terra1sux7jjk9vfd0q6z0l99wpg07yd0wme0ac9le40' THEN 'The Crunks'
  				 WHEN project = 'terra1fygyguq256d779hh55vf9xhty9g9wpfrl8gn2z' THEN 'Terra One'
  				 WHEN project = 'terra1y4shq4q8t4d98njay3dwc7ww5v2kg08sytyl3n' THEN 'Terrapin Eggs'
  				 WHEN project = 'terra1je56ff4p2e90j9rtvfy4xy7fja50sgehx48827' THEN 'Bullrun Girlfriends'
  				 ELSE '**NO NAME**' END AS "Project Name",
  				project as "Contract Address",
				round(amountt,2) as "Total Volume (LUNA)"
from qmain
order by 3 desc
```


THIS WORKS
```
select  block_timestamp,
        block_id,
        tx_id,
        msg_value:execute_msg:mint:extension:name::string                as name,
        msg_value:execute_msg:mint:token_id::string                      as tokenid,
        msg_value:execute_msg:mint:extension:attributes[0]:value::string as rarity,
        msg_value:execute_msg:mint:extension:attributes[1]:value::string as rank,
        msg_value:execute_msg:mint:extension:attributes[2]:value::string as shower,
        msg_value:execute_msg:mint:extension:attributes[3]:value::string as distance,
        msg_value:execute_msg:mint:extension:attributes[4]:value::string as crystal1,
        msg_value:execute_msg:mint:extension:attributes[5]:value::string as crystal2,
        msg_value:execute_msg:mint:extension:attributes[6]:value::string as crystal3,
        msg_value:execute_msg:mint:extension:attributes[7]:value::string as weight,
        msg_value:execute_msg:mint:extension:attributes[8]:value::string as origin,
        msg_value:execute_msg:mint:extension:attributes[9]:value::string as essence
  from  terra.msgs 
  where msg_value:contract::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' 
  and   msg_value:sender::string = 'terra1v7v2nqs7flrpqqam7l5ulvnva8ly8j653sw4n3'
  and   msg_value:execute_msg:mint is not null
  and   tx_status = 'SUCCEEDED')
,  
LEVANA AS (
  SELECT
*,
date_trunc('day', block_timestamp) as date_hour,
msg_value:contract::string, -- terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t
msg_value:execute_msg:execute_order:order:order:maker_asset:amount::string as ntf_amount, -- 1
msg_value:execute_msg:execute_order:order:order:maker_fee::string as maker_fee, -- 0
msg_value:execute_msg:execute_order:order:order:nonce::string as nonce, -- 74160819
msg_value:execute_msg:execute_order:order:order:taker::string as taker, -- terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t RandomEarth Sale
msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string as contract_addr, -- Levana Dragons terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v
msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:token_id::string as token_id, -- 15573
msg_value:sender as sender, -- terra14rhawx74jpx7m6795g74v3syar3c5shefexufv
msg_value:execute_msg:execute_order:order:order:taker_asset:amount::string/pow(10,6) as luna_amount -- 1475000
From terra.msgs
--sampple ts where tx_id = 'FCF8DB32EA4A2A87B1D811E91B0CA1558CD08CDF93571BAB454EB2FFB20C3753'
WHERE msg_value:execute_msg:execute_order:order:order:taker::string = 'terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t' -- RE Sale Contact
AND msg_value:execute_msg:execute_order:order:order:maker_asset:info:nft:contract_addr::string = 'terra1chrdxaef0y2feynkpq63mve0sqeg09acjnp55v' -- Levana 
AND tx_status = 'SUCCEEDED'
)


  ,
lastly as (SELECT
date_hour,
sum(ntf_amount) as nft_traded,
  token_id,
sum(luna_amount) as luna_vol,
  avg(luna_amount) as luna_avg

FROM LEVANA 
GROUP BY token_id, date_hour
ORDER BY 1 desc)
  
  select * from lastly 
  left join meteor_traits 
  on lastly.token_id = meteor_traits.TOKENID 
```

