---
description: Credits - brian_#3619
---

# Query - Sales

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
