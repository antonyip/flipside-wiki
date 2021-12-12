---
description: Credits - brian_#3619
---

# Query - Sales

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
