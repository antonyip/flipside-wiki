# QUERY - Validators

## Validator Rewards

{% embed url="https://app.flipsidecrypto.com/velocity/queries/890ec4ed-725e-47b0-89b7-2504b8551452" %}
Credits: AD#5391
{% endembed %}

## Validator Addresses

```
WITH validatornames as 
(select 'terravaloper1fg5g8acntt90n9303cm5fjza9s3newleq60zt9' as address, 'Galactic Lounge 🥃 🍸 🍹' as name from terra.transactions 
union select 'terravaloper1svcgzkp4lhvvltce5uk73tnwxfrj6nlka4vm3x' as address, 'KK Validator | == gp airdrop ==' as name from terra.transactions 
union select 'terravaloper1audgfvmgt0js54p3s8kj3r40uwej6vy2tv6rrw' as address, 'FreshLUNA.com Enterprise Validator' as name from terra.transactions 
union select 'terravaloper1x4ce4fhqdnu8j7hrp64qmthumsvuhlq8y0kvx4' as address, 'MissionControl' as name from terra.transactions 
union select 'terravaloper13rt78f5rclczn4gsxxfa7r50q0cvjjhvdt2zzj' as address, 'BinanceStaking' as name from terra.transactions 
union select 'terravaloper120ppepaj2lh5vreadx42wnjjznh55vvktp78wk' as address, 'Allnodes ⚡️ 0% fee' as name from terra.transactions 
union select 'terravaloper1259cmu5zyklsdkmgstxhwqpe0utfe5hhyty0at' as address, 'Orion.Money' as name from terra.transactions 
union select 'terravaloper1kprce6kc08a6l03gzzh99hfpazfjeczfpzkkau' as address, 'Certus One' as name from terra.transactions 
union select 'terravaloper1qd0uk3wrw73x662y2gx4kaulrzlcky6275gl5s' as address, 'Talis Protocol' as name from terra.transactions 
union select 'terravaloper1vkdp7amtzcde4awykg8xuph0sq89xghpkxyzye' as address, 'Aardvark' as name from terra.transactions 
union select 'terravaloper1qt7kqljer7fxzudqdyhx87l7wreeef53s2smsa' as address, 'Bison Trails' as name from terra.transactions 
union select 'terravaloper1pux4j3hm2am302qr40u5leh5lsgfvgjsksnthm' as address, 'Centauri Alpha' as name from terra.transactions 
union select 'terravaloper1t90gxaawul292g2vvqnr3g0p39tw5v6vsk5p96' as address, 'Terra Bites' as name from terra.transactions 
union select 'terravaloper1hqyygjq0vdqk0xdpkffgamzr4f7tqqg5u9mg66' as address, 'Angel Protocol' as name from terra.transactions 
union select 'terravaloper19ne0aqltndwxl0n32zyuglp2z8mm3nu0gxpfaw' as address, 'Terra-India' as name from terra.transactions 
union select 'terravaloper1uymwfafhq8fruvcjq8k67a29nqzrxnv9m6m427' as address, 'Terran Stakers' as name from terra.transactions 
union select 'terravaloper19xe62428tlfesdym0zn5wx9slyefqjp00r67kw' as address, 'MoonletWallet' as name from terra.transactions 
union select 'terravaloper1t76s5v5vjawkrr70sh55flpxfcmc3k304qrpvr' as address, 'GalaxyDigital' as name from terra.transactions 
union select 'terravaloper1qqu376azltyc5wnsje5qgwru5mtj2yqdhar97v' as address, 'TERRA-FIRMA' as name from terra.transactions 
union select 'terravaloper1rn9grwtg4p3f30tpzk8w0727ahcazj0f0n3xnk' as address, 'GT Capital' as name from terra.transactions 
union select 'terravaloper1r843mpk5zzkfgtnduskd0dzgeltv0n503ckzy6' as address, 'flipside' as name from terra.transactions 
union select 'terravaloper12qvrr6j7u3z5el5uuwg99ftx3jru5py6027gfx' as address, 'Nodeasy' as name from terra.transactions 
union select 'terravaloper12g4nkvsjjnl0t7fvq3hdcw7y8dc9fq69nyeu9q' as address, 'PFC' as name from terra.transactions 
union select 'terravaloper1p94a6vwl9dkd98cyrlmzf6ydjdgfvamyhu33fa' as address, 'LunaOrbit' as name from terra.transactions 
union select 'terravaloper1ryhpcmnkeqa6umrp06g9782qjwdqc8wfe3vada' as address, 'SCB 10X' as name from terra.transactions 
union select 'terravaloper1mpmn2y9qw4dn6z2q3a7hy4c3wjztmvu7wz4r4u' as address, 'THORchain.BULL &amp;&nbsp;0xVentures.org' as name from terra.transactions 
union select 'terravaloper18hpew39uymssr52w8euxqh4zrrjt02x7k0jmhk' as address, 'OneStar' as name from terra.transactions 
union select 'terravaloper1wcdv9kccp8jjy8r6uc5gxkc3ymqpeyj6w2nmja' as address, 'The Valhalla Express' as name from terra.transactions 
union select 'terravaloper155x8vngnz4u2ce3fs6dvu027v8w90jqdjtdp3h' as address, 'Blockdaemon' as name from terra.transactions 
union select 'terravaloper123gn6j23lmexu0qx5qhmgxgunmjcqsx8gmsyse' as address, 'Staking Fund' as name from terra.transactions 
union select 'terravaloper1jkg3wy5q9q6jlshjf2r6p9nf4flwtr6hp30rjk' as address, 'Neptune Finance' as name from terra.transactions 
union select 'terravaloper1g6g0v23c6tv75ygk5za4s2ewwestdfj0k2cy2x' as address, 'StakeSabai' as name from terra.transactions 
union select 'terravaloper1542ek7muegmm806akl0lam5vlqlph7spflfcun' as address, 'blockscape' as name from terra.transactions 
union select 'terravaloper1wqcc5g3k3mqg96pgvemzstmhkf42lt8358v6rd' as address, 'CAPAPULT' as name from terra.transactions 
union select 'terravaloper15zcjduavxc5mkp8qcqs9eyhwlqwdlrzy6jln3m' as address, 'B-Harvest' as name from terra.transactions 
union select 'terravaloper1v5hrqlv8dqgzvy0pwzqzg0gxy899rm4kdur03x' as address, 'DokiaCapital' as name from terra.transactions 
union select 'terravaloper1krj7amhhagjnyg2tkkuh6l0550y733jnjnnlzy' as address, 'Terran One' as name from terra.transactions 
union select 'terravaloper15s5d4lm0n75af9jxwawqzl73trnrypdslajxz4' as address, 'Mosaic' as name from terra.transactions 
union select 'terravaloper1vqnhgc6d0jyggtytzqrnsc40r4zez6tx99382w' as address, '🌐 KysenPool Moon 🌕' as name from terra.transactions 
union select 'terravaloper173de34wwvak6d4829h5vmxvm98y5vl08tmfgrq' as address, 'Rockaway Blockchain Fund' as name from terra.transactions 
union select 'terravaloper1pc0gs3n6803x7jqe9m7etegmyx29xw38aaf3u7' as address, 'Staker Space' as name from terra.transactions 
union select 'terravaloper1yad8pjqp93gvwkxa2aa5mh4vctzfs37ekjxr4s' as address, 'healings' as name from terra.transactions 
union select 'terravaloper1hqzf3tnw0py69xd5swwr3c7tqcumwjzdzqca7l' as address, 'wave' as name from terra.transactions 
union select 'terravaloper1xuxwc867udr9k84zzqhaflf9sc00svvmj5e4fy' as address, 'moonshot' as name from terra.transactions 
union select 'terravaloper1xetqge5kmatfk6223hcfgf8z3tnukmjhrewxru' as address, 'Heavy Metal Finland' as name from terra.transactions 
union select 'terravaloper1vqegsqhe8q06t6jwgvww0qcr2u6v6g9xrwjnmw' as address, 'Inotel' as name from terra.transactions 
union select 'terravaloper1ya23p5cxtxwcfdrq4dmd2h0p5nc0vcl96yhjra' as address, 'BTC.Secure' as name from terra.transactions 
union select 'terravaloper12jpzzmwthrljcvm48adncspxtchazkl8vah7u4' as address, 'Synergy Nodes - Glory' as name from terra.transactions 
union select 'terravaloper1fhx7y75643tze8dxf4m9gwhkxn955q8r7vxjel' as address, 'SolidStake' as name from terra.transactions 
union select 'terravaloper1nnm4qx2ytff5gy7a82yh4nw4tnez4s38p4y0g9' as address, 'Protoss One' as name from terra.transactions 
union select 'terravaloper1jkqr2vfg4krfd4zwmsf7elfj07cjuzss30ux8g' as address, 'Forbole' as name from terra.transactions 
union select 'terravaloper198c72uxt9p8r2u5y6zha4390qjkayvjr3gduxx' as address, 'Zerg One' as name from terra.transactions 
union select 'terravaloper16tc3c9u6yj5uuhru32pvs0pahfwraurpypz7vj' as address, 'block42' as name from terra.transactions 
union select 'terravaloper1y7px9rdkn3xeh2hyfvk9pveygsk4v7lmf3d9w3' as address, 'ChainofSecrets.org' as name from terra.transactions 
union select 'terravaloper19z68rv3d7dzvvtlxzma89jxsrssf9j36ylsfwc' as address, 'Galactic Punks Validator' as name from terra.transactions 
union select 'terravaloper175hhkyxmkp8hf2zrzka7cnn7lk6mudtv4uuu64' as address, 'DSRV - CHAISCAN.com' as name from terra.transactions 
union select 'terravaloper1alpf6snw2d76kkwjv3dp4l7pcl6cn9uyt0tcj9' as address, 'Smart Stake' as name from terra.transactions 
union select 'terravaloper1a9q6jl792qg36cp025ccjtgyf4qxrwzqjkmk5d' as address, 'stake.systems' as name from terra.transactions 
union select 'terravaloper1c9ye54e3pzwm3e0zpdlel6pnavrj9qqvq89r3r' as address, 'StakeWith.Us' as name from terra.transactions 
union select 'terravaloper1j27nm2gjm0m4lsye8lspa46rax0rw4fge23nnr' as address, 'Luna Station 88' as name from terra.transactions 
union select 'terravaloper13g7z3qq6f00qww3u4mpcs3xw5jhqwraswraapc' as address, 'everstakeone' as name from terra.transactions 
union select 'terravaloper15khv8dsaxqmf7nwu4jdlp9slxl7aczte3x068c' as address, 'ISS' as name from terra.transactions 
union select 'terravaloper1dcrq2xwuhea9hm5xfuydjuwgz6gm7vdjz7e4uf' as address, 'Mr.K' as name from terra.transactions 
union select 'terravaloper1dfcptsy9x4wzhpv0m79v47ladgj02yyufq3d50' as address, 'Terra World' as name from terra.transactions 
union select 'terravaloper1nwrksgv2vuadma8ygs8rhwffu2ygk4j24w2mku' as address, 'Stakin' as name from terra.transactions 
union select 'terravaloper1sym8gyehrdsm03vdc44rg9sflg8zeuqwfzavhx' as address, 'syncnode' as name from terra.transactions 
union select 'terravaloper12mcn4pj7d8yeff0xfedcthqe9gs3vwc2tn8sy2' as address, 'Go-Terra' as name from terra.transactions 
union select 'terravaloper13ncmrxrf8r0gkztpu7hxvs0hvfuqnq4kd7qr49' as address, 'MCF' as name from terra.transactions 
union select 'terravaloper1v3dey0ha6vdnssru88t2m5fzy7vuvs7emt37an' as address, 'Legend.X' as name from terra.transactions 
union select 'terravaloper1yxkfgpyu6m2wkgw4ljuky9lvn59r3wn0ksfvyl' as address, 'CoinBevy' as name from terra.transactions 
union select 'terravaloper1jyjg55hzsh0f4xymy0kuuan30pp4q75ruqmvyt' as address, 'kytzu' as name from terra.transactions 
union select 'terravaloper1n7pkcal0jkp0ac9r338qp9cm5x6cakfnremtnt' as address, 'AUDIT.one' as name from terra.transactions 
union select 'terravaloper193zuma3tk69kvffz9nqnca7z99tz7ej5ze9s7k' as address, 'NITAWA' as name from terra.transactions 
union select 'terravaloper1xl2ujgt7f6xn8v26rjkhy4f20x5plc3nq6nql7' as address, 'Luna Rewards' as name from terra.transactions 
union select 'terravaloper1ptyzewnns2kn37ewtmv6ppsvhdnmeapvgk6d65' as address, 'WeStaking' as name from terra.transactions 
union select 'terravaloper1qfx03ywz9hhxupv73lq06da6jjrdwwrl33yp8e' as address, '🤑 uGaenn ⛅' as name from terra.transactions 
union select 'terravaloper1aw0znxtlq0wrayyz7wppz3qnw94hfrmnnrcxja' as address, 'RockX' as name from terra.transactions 
union select 'terravaloper1tusfpgvjrplqg2fm7wacy4slzjmnzswcfufuvp' as address, 'ATEAM' as name from terra.transactions 
union select 'terravaloper1khfcg09plqw84jxy5e7fj6ag4s2r9wqsgm7k94' as address, '01node' as name from terra.transactions 
union select 'terravaloper108lmrztvc3pc3w774shgvpry4d3lf79k2ummna' as address, 'Stakely.io' as name from terra.transactions 
union select 'terravaloper1magm90vzn4t75da3jadmahcp5ya075ez9t6rwa' as address, 'Craig' as name from terra.transactions 
union select 'terravaloper1rjmzlljxwu2qh6g2sm9uldmtg0kj4qgyy9jx24' as address, 'Aura Stake' as name from terra.transactions 
union select 'terravaloper1ullpeaj86f2y26gpvg09szznfve7tqur8ddala' as address, 'Uranus' as name from terra.transactions 
union select 'terravaloper1chscwnxzcnd8qvk76efjd6dd73gf945dh4qryr' as address, 'MANTRA DAO' as name from terra.transactions 
union select 'terravaloper1smkgwm78aqf0ja3qvtqwngzczpcekudvtluv9q' as address, 'Cosmic Validator' as name from terra.transactions 
union select 'terravaloper1km83qf6kwmzt32m4zha4spnuhj56kw2jcyg35r' as address, '100 Luna raffle - 🌕🔥 Luna Burner 🚀' as name from terra.transactions 
union select 'terravaloper15urq2dtp9qce4fyc85m6upwm9xul30496sgk37' as address, 'Chorus One' as name from terra.transactions 
union select 'terravaloper1d3fv2cjukt0e6lrzd8d857jatlkht7wcp85zar' as address, 'Cives lunares - lunarcitizens.io' as name from terra.transactions 
union select 'terravaloper12x0uekrjre057h0vyrf9w8mkz6paf32qvn0q84' as address, 'BlockStake.xyz' as name from terra.transactions 
union select 'terravaloper1f2t96sz9hnwsqnneux6v28xfgn07pkxjduvwjz' as address, ' BlockNgine 100% slash protected' as name from terra.transactions 
union select 'terravaloper1zc9uadde55t4k3aw9uvgpkhwpsyzkq3k20g38r' as address, 'Autism Staking 🧩' as name from terra.transactions 
union select 'terravaloper1av4m4rxeh2vsdm76lnwd0ysw0mu6eufjp0ta8u' as address, 'Nexus Event' as name from terra.transactions 
union select 'terravaloper1565r942vpnpqtrsmhxxwvel8j2m40zgsppvl2j' as address, 'Sarah Kerrigan' as name from terra.transactions 
union select 'terravaloper1hwucxmeqtytu9nq54e9aarwrhzsej6w0hrrwz3' as address, 'TerraDactyl' as name from terra.transactions 
union select 'terravaloper1y7e9grrpt8kp0uk2v6mqd9pd0zdnkcwx4tmexv' as address, 'Un Fuego' as name from terra.transactions 
union select 'terravaloper12j25g6uutxrry2zvwnyte6g04kylrm5k587lpl' as address, 'Interdimensional Cable' as name from terra.transactions 
union select 'terravaloper1me4u0au0gr29av3wmvr3zk4m0rkerjll7rd9ng' as address, 'Top Shelf' as name from terra.transactions 
union select 'terravaloper1de6t7xn6mrrckxgpku6kypgyf4wc2fcnuk6jl6' as address, 'Leviathan' as name from terra.transactions 
union select 'terravaloper1x92rzuf9z7t359p3zackj0deezkhs3vc9x9y4t' as address, 'StakeBowl' as name from terra.transactions 
union select 'terravaloper1cga2xslx7j07fan9ud4p4sg5ha72gtwewxxyg7' as address, 'Moon Coin' as name from terra.transactions 
union select 'terravaloper1va2ew92dtkhffduswr83elf3nfvl4xg48vyp7v' as address, 'NOD Games' as name from terra.transactions 
union select 'terravaloper1fjuvyccn8hfmn5r7wc2t3kwqy09zzp6tyjcf50' as address, 'DELIGHT' as name from terra.transactions 
union select 'terravaloper1tze7t69lc8dwngkxgv2z3cm9zg907suqn6y8mj' as address, 'Chaos Protocol' as name from terra.transactions 
union select 'terravaloper1dg7zhmt4g4zq74y4tksq4xfzf5pwx4cnngavjk' as address, 'Marte Cloud' as name from terra.transactions 
union select 'terravaloper13slfa8cc7zvmjt4wkap2lwmlkp4h3azwltlj6s' as address, '✅ CryptoCrew Validators #IBCgang' as name from terra.transactions 
union select 'terravaloper144l7c3uph5a7h62xd8u5et3rqvj3dqtvvka2fu' as address, 'P2P.ORG - P2P Validator' as name from terra.transactions 
union select 'terravaloper1mgdsc0get3w984h03a02zy6gmg3kgqtfqs3tky' as address, '🚀 LambdaCore | 🎁airdrop📦' as name from terra.transactions 
union select 'terravaloper1a3r6va8hnyzsq6kr75lyge05d0dtjv6e8wvzra' as address, 'Hypersphere Digital' as name from terra.transactions 
union select 'terravaloper162892yn0tf8dxl8ghgneqykyr8ufrwmcs4q5m8' as address, 'Luna Maximalists' as name from terra.transactions 
union select 'terravaloper15cupwhpnxhgylxa8n4ufyvux05xu864jcv0tsw' as address, 'Figment' as name from terra.transactions 
union select 'terravaloper1d0dupc4hvl4nnfky6vqp4xyeunejgsjas9km7q' as address, 'DACM' as name from terra.transactions 
union select 'terravaloper19hflr9ay8usqxsxm4zzrsxfy3xz7hp6kv4ydnd' as address, 'Orbital Command' as name from terra.transactions 
union select 'terravaloper1d0vfj9zvxfgcm4yt4ze4u35mvhj57eg2ku2ekv' as address, 'Easy 2 Stake' as name from terra.transactions 
union select 'terravaloper1p54hc4yy2ajg67j645dn73w3378j6k05vmx9r9' as address, 'hashed' as name from terra.transactions 
union select 'terravaloper17juxr8d54kfscas5jmtaztfcrsdhalm0eh7u4g' as address, 'BridgeTower' as name from terra.transactions 
union select 'terravaloper12kfeqrflptmlz5qj8agrm2ze6dzss3crm7uevf' as address, 'HuobiPool' as name from terra.transactions 
union select 'terravaloper1tdkh85vv7vsvav93elmx6qsywuu22amc60u3sa' as address, 'setten.io' as name from terra.transactions 
union select 'terravaloper1xc58asjmdhaqeargcaev3muem2xtp36x8ru3n5' as address, 'Pantera Capital' as name from terra.transactions 
union select 'terravaloper1c6gve6zhye5690563wxmvns7mugz6plu4aj7d3' as address, 'Arrington XRP Capital' as name from terra.transactions 
union select 'terravaloper1hme9uynnxf0ga72xmwtdgztt2lmg0jlqjgsj5n' as address, '8moon' as name from terra.transactions 
union select 'terravaloper1h6rf7y2ar5vz64q8rchz5443s3tqnswrpf4846' as address, 'Staked' as name from terra.transactions 
union select 'terravaloper1u7cfwp620pn8tjfth92t5dry3mhd3etc2utr94' as address, 'Crypto Plant' as name from terra.transactions 
union select 'terravaloper1kgddca7qj96z0qcxr2c45z73cfl0c75paknc5e' as address, 'ChainLayer' as name from terra.transactions 
union select 'terravaloper1rf9xakxf97a49qa5svsf7yypjswzkutqfhnpn5' as address, 'gazua' as name from terra.transactions 
union select 'terravaloper18p7kdpvpsp3muz93ww7ej72wyrrdja2l7a7mfk' as address, 'bc1' as name from terra.transactions 
union select 'terravaloper12079m57cew2v02zs624zvyed5479an9wxh03fy' as address, '0base.vc' as name from terra.transactions 
union select 'terravaloper1p72vswk5zfzzr7myhrerm78ty5tjc8ypl259tm' as address, 'Accomplice Blockchain' as name from terra.transactions 
union select 'terravaloper1lm604mtdalpd9z46486acqlshns2urquwvkmq8' as address, 'Staky.io' as name from terra.transactions 
union select 'terravaloper18jv83kckd0r8ht9fwsqzyvljcd4h4pj9ufntwe' as address, 'InfStones' as name from terra.transactions 
union select 'terravaloper1t0z9y2p26qzsh06f2l2kn2v8hqtkyd33s409ey' as address, 'Stake5 Labs' as name from terra.transactions 
union select 'terravaloper1jfndgwuwewn6363w5j5h5wpek3g6ucss4v84kf' as address, 'DONT DELEGATE' as name from terra.transactions 
union select 'terravaloper1gytqku2dl53w48pdusj9k6t00nfl5nsrhjpr5d' as address, 'Hanko' as name from terra.transactions 
union select 'terravaloper122jtp99q03vjdq2d63fgtmsjyndhkh3whaqaas' as address, 'GLab' as name from terra.transactions 
union select 'terravaloper1wpvlm4278zysnmfkamjnceezdquguk6s92azgq' as address, 'qwack' as name from terra.transactions 
union select 'terravaloper105pz70scujjd84rfzj4zlqkv3j588nahnnwdde' as address, 'StakeMix' as name from terra.transactions 
union select 'terravaloper157m8nyw8ne3jz0dgdys6chp98jlpuhggp35ev5' as address, 'dxmterranode' as name from terra.transactions 
union select 'terravaloper14jywaln0sdh8lpc7jtyllqfp3mg5sjw2nsx0f9' as address, 'coaction-capital' as name from terra.transactions 
union select 'terravaloper1vv4y54wczzk99ga65uvy7555n5q68gswcmdvj2' as address, 'EZStaking.io' as name from terra.transactions 
union select 'terravaloper15qjn7ke9s47qn4mte3lerkxtjjgp38n5qquzsu' as address, 'Masternode24.de' as name from terra.transactions 
union select 'terravaloper1k4ef8m95t7eq522evmmuzvfkpla04pezmu4j7k' as address, 'Bit Cat🐱' as name from terra.transactions 
union select 'terravaloper1l8kzrd460yxcfshllr47n580qtjgp875g8ancf' as address, 'Luna Station 81 (Please redelegate)' as name from terra.transactions 
union select 'terravaloper1el72mmska9fd4w9ehst0v4dkd4wqp288hvfwfh' as address, 'NonceTerra' as name from terra.transactions 
union select 'terravaloper1ch2k5euzh2smu2f5jjma9fuvsn2pu2wk2v5p4r' as address, 'mvl' as name from terra.transactions 
union select 'terravaloper1cc92ptawsp9363aae9wrp2xm6zm9fmucw9mucd' as address, '“BinanceStacking”' as name from terra.transactions 
union select 'terravaloper1npv0gns884njlnpd7szhh028vdh2agzxmddk2k' as address, 'Khazad-dûm' as name from terra.transactions 
union select 'terravaloper19wrdftpur6jahna2f7286l7u4m4n3m78yp7vun' as address, 'va1' as name from terra.transactions 
union select 'terravaloper1gh7wpfpsjrqnash5uc84z4njt95y9g5nh3uqzx' as address, 'Genesis Lab' as name from terra.transactions 
union select 'terravaloper1qrs8d7z4w0gz05c3llz3xsn5eh0tc9rejesk0k' as address, 'Cosmos Validator' as name from terra.transactions 
union select 'terravaloper1p3uz3qztr2faqqq0h20qdwmvkc3ugupgyk4qyg' as address, '#decentralizehk - inactive, please redelegate' as name from terra.transactions 
union select 'terravaloper1rucuack65khwltlw5pzc2ek3lnppp94qkj5ffa' as address, '“IRRpool”' as name from terra.transactions 
union select 'terravaloper1jlxv4hnf2mtym9x4fg7dsepgnt47rgfan9x6cc' as address, 'TERRA-LUNA.DLINODES.COM' as name from terra.transactions 
union select 'terravaloper15vqlw5zukqzgnh7x8naq6hpc88rc77y0aajdw2' as address, 'MyCointainer' as name from terra.transactions 
union select 'terravaloper1rlxlvmm0fhpkfcu95gvzdzlcxyy9xycufvchha' as address, 'rocklords' as name from terra.transactions 
union select 'terravaloper1r08m7m7uwre343kveewluq4rh9ykup306q0y9d' as address, 'uber-validator' as name from terra.transactions 
union select 'terravaloper103ra79dl2un2ltknhyz7crm5y29g4vhmycfwv9' as address, 'NEOWIZ' as name from terra.transactions 
union select 'terravaloper1s00gyl6dlz6gkfj0mwcrcffu8mrw8dgr9k3hkr' as address, 'SafePoint' as name from terra.transactions 
union select 'terravaloper1nrhlk67k38k9v7yatl0a30q287dhncjjkx5l0t' as address, 'Feel Mining' as name from terra.transactions 
union select 'terravaloper1jsdfyz8uhw2nd7cl45709w40r268phmvxam8eh' as address, 'Bi23 Labs' as name from terra.transactions 
union select 'terravaloper1guksxgm0qxm00kaf35myxn263ws9l6ykl977cn' as address, 'Pillow Staking - No Commission' as name from terra.transactions 
union select 'terravaloper1dkw5zp0jf7v7xzut5a8kuaeksg9xufahkt5atj' as address, 'ChainodeTech' as name from terra.transactions 
union select 'terravaloper1fkftfalmgcc5weq90sf2fch9y5vlpxvjv32yfr' as address, 'change' as name from terra.transactions 
union select 'terravaloper1f699dxaftg4pxfqtwzyreyxgaznk922zukuhyk' as address, 'Just-Mining' as name from terra.transactions 
union select 'terravaloper1h7n8r8sjgrppn396r2znvwvxm9saps93334mc5' as address, 'RHIZOME DAO' as name from terra.transactions 
union select 'terravaloper1lf3zrmdha5nk434nkezzg6m4s5yhfka09wfuaq' as address, 'Luna Wolfpack' as name from terra.transactions 
union select 'terravaloper1vhm0l52y83vsqr60vt7vhxgsjlfyhf3h2mgfpe' as address, 'Tavis Digital' as name from terra.transactions 
union select 'terravaloper18fk2ye6m5wnnfrarpwycunnw0ls8564zw37myg' as address, 'stake.zone' as name from terra.transactions 
union select 'terravaloper1rq65gnyxaxv2mzmna4rvpacyu7a4qanjtjj0k2' as address, 'Easy Company' as name from terra.transactions 
union select 'terravaloper1rnna7hcf88nzfqmc362egmmp76yeyzlepx5vtr' as address, 'JT Stakers | 0% Commission' as name from terra.transactions 
union select 'terravaloper186dsseaecl6scdru3ldtwq0f5stez99vs6yfah' as address, 'MOON' as name from terra.transactions 
union select 'terravaloper1y62j08pv27uwjwg987wsvza5suujhyxau6c8xr' as address, 'unbounding, do not delegate' as name from terra.transactions 
union select 'terravaloper12ce886lv4muzt09rgehsta8433d8vz7cxmha0p' as address, 'Coverlet' as name from terra.transactions 
union select 'terravaloper197d5p7lpn34r2uff0drx78zf5e4jle4wwthzyd' as address, 'Shutting down - please undelegate' as name from terra.transactions 
union select 'terravaloper13307pxehvt0qply3kw9vk578u4az0u4mu9eef4' as address, 'DUST Foundation' as name from terra.transactions 
union select 'terravaloper16vz92wm3fahqepa5s7jt0ml8h337umycjzwycv' as address, 'nomercy' as name from terra.transactions 
union select 'terravaloper1ltta9hz8hrd5dnqnqnt5sfcdl4kx8m0afptshu' as address, 'SmartFellas' as name from terra.transactions 
union select 'terravaloper10ahmn0ucd9selcv77rwysx5pvd607z04zde7uh' as address, 'StakeLab' as name from terra.transactions 
union select 'terravaloper1lda78gzrjx0rsadtdk0zn4v7awtz6m9lrd5ez9' as address, 'Polychain Labs' as name from terra.transactions 
union select 'terravaloper1s5cyxwl36atv65m03pumrp9alhn2xdtzw5ug4l' as address, 'RnodeC' as name from terra.transactions 
union select 'terravaloper15hg3m4ch6n0yt4uq6nsadqszlna95am904vzv9' as address, 'BTCSterra' as name from terra.transactions 
union select 'terravaloper1cn2qhqs4g0fzxn8j2lhr3vwffc86s0k65hv90j' as address, 'Notional' as name from terra.transactions 
union select 'terravaloper1ltwln4yqytkfzn6868xazlhg7vlzdcf96ly9zs' as address, 'BasBlock' as name from terra.transactions 
union select 'terravaloper1a2wp3yn3d783q3cmmj9jda7t93088m6z3ny6u5' as address, 'CitadelSystems.eu' as name from terra.transactions 
union select 'terravaloper166fh7594tsp0yrg3c5c4najmehd5s54tkpsawy' as address, 'MoonStation' as name from terra.transactions 
union select 'terravaloper1s9q2t9zf8zyjg9g45sn6f6t06kwvgspsl4yz9s' as address, 'Masternode24.de' as name from terra.transactions 
union select 'terravaloper1uf4k2y293qss3tfhdrlz7whsu5xj2dpjtuxuuq' as address, 'InfiniteHeig.ht' as name from terra.transactions 
union select 'terravaloper10cpv0r3z2aue92d0h0tlsp6p2etmh7xu4vaa46' as address, 'Blockware Solutions' as name from terra.transactions 
union select 'terravaloper1jaeca6lv7hn6r76ed770vzamhx09956x77q6wr' as address, 'Moonwalk' as name from terra.transactions 
union select 'terravaloper1qr8ewxc0xx2vuq7jhe2evsde2k4c4cku6wf23h' as address, 'Secure Secrets' as name from terra.transactions 
union select 'terravaloper1gwn2dpjfcuxhaewwn709txfffrvewuq22w32fj' as address, 'STAKENODE' as name from terra.transactions 
union select 'terravaloper1hxyx4s2uwfe8gq9a8h6gm0mkyruy8djp9yvz3z' as address, 'F U L L . M O O N' as name from terra.transactions 
union select 'terravaloper1xptfsrmkhw0s4kql4ldnzake83j8dgvxm3p952' as address, 'RnodeC' as name from terra.transactions 
union select 'terravaloper129zazmhhzap0nplylk00ujxlguf5ne7nkmaep8' as address, 'PMCapital' as name from terra.transactions 
union select 'terravaloper1whk8em6gz22q9a8fk027ctvud79z5mj3meadjf' as address, 'L1 Anchorage' as name from terra.transactions 
union select 'terravaloper17gevmwa2ejzqj6wjvmee9tsfvuf3xlct3f090q' as address, 'L1Anchorage' as name from terra.transactions 
union select 'terravaloper1av2j80jeyuxmzgsm840rkh08c5vyy3tmr3q0g8' as address, 'To the Moon' as name from terra.transactions 
)

select * from validatornames
```
