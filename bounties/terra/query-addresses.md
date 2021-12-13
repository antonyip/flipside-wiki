---
description: Credits - brian_#3619
---

# QUERY - Addresses

```
(select distinct 
              CASE 
              WHEN contract = 'terra1cgg6yef7qcdm070qftghfulaxmllgmvk77nc7t' THEN 'Anchor Price Oracle'
              WHEN contract = 'terra1eek0ymmhyzja60830xhzm7k7jkrk99a60q2z2t' THEN 'RandomEarth'
              WHEN contract = 'terra1sepfj7s0aeg5967uxnfk4thzlerrsktkpelm5s' THEN 'Anchor Market'
              WHEN contract = 'terra1w8t3fkm80sud5z9yr86tfcxz675mj85p8prauc' THEN 'Mirror Relay'
              WHEN contract = 'terra1tndcaqxkpc5ce9qee5ggqf430mr2z3pefe5wj6' THEN 'LUNA-UST Pair Terraswap'
              WHEN contract = 'terra1t6xe0txzywdg85n6k8c960cuwgh6l8esw6lau9' THEN 'Mirror Oracle'
              WHEN contract = 'terra183uw6660lrpzfh0rdfa3rrn24m3ke7qffgmfrd' THEN 'Mirror Relay'
              WHEN contract = 'terra14z56l0fp2lsf86zy3hty2z47ezkhnthtr9yq76' THEN 'Anchor Token (ANC)'
              WHEN contract = 'terra146ahqn6d3qgdvmj8cj96hh03dzmeedhsf0kxqm' THEN 'Anchor Airdrop'
              WHEN contract = 'terra1hzh9vpxhsk8253se0vv5jj6etdvxu3nv8z07zu' THEN 'aUST Token'
              WHEN contract = 'terra1kalp2knjm4cs3f59ukr4hdhuuncp648eqrgshw' THEN 'Mirror Airdrop'
              WHEN contract = 'terra1kcthelkax4j9x8d3ny6sdag0qmxxynl3qtcrpy' THEN 'Pylon Token (MINE)'
              WHEN contract = 'terra15gwkyepfc6xgca5t5zefzwy42uts8l2m4g40k6' THEN 'Mirror Token (MIR)'
              WHEN contract = 'terra17f7zu97865jmknk7p2glqvxzhduk78772ezac5' THEN 'Mirror Staking'
              WHEN contract = 'terra1kc87mu460fwkqte29rquh4hc20m54fxwtsx7gp' THEN 'BLuna Token'
              WHEN contract = 'terra1vs9jr7pxuqwct3j29lez3pfetuu8xmq7tk3lzk' THEN 'Assert Limit Order Terraswap'
              WHEN contract = 'terra13xujxcrc9dqft4p9a8ls0w3j0xnzm6y2uvve8n' THEN 'StarTerra Token (STT)'
              WHEN contract = 'terra1ud39n6c42hmtp2z0qmy8svsk7z3zmdkxzfwcf2' THEN 'Pylon Airdrop'
              WHEN contract = 'terra1tmnqgvg567ypvsvk6rwsga3srp7e3lg6u0elp8' THEN 'Anchor Overseer'
              WHEN contract = 'terra1dy9kmlm4anr92e42mrkjwzyvfqwz66un00rwr5' THEN 'Valkyrie Token (VKR)'
              WHEN contract = 'terra12897djskt9rge8dtmm86w654g7kzckkd698608' THEN 'Nexus Token (PSI)'
              WHEN contract = 'terra178jydtjvj4gw8earkgnqc80c3hrmqj4kw2welz' THEN 'MINE-UST Pair Terraswap'
              WHEN contract = 'terra19pg6d7rrndg4z4t0jhcd7z9nhl3p5ygqttxjll' THEN 'STT-UST Pair Terraswap'
              WHEN contract = 'terra1kehar0l76kzuvrrcwj5um72u3pjq2uvp62aruf' THEN 'Spectrum Mirror Farm'
              WHEN contract = 'terra1ude6ggsvwrhefw2dqjh4j6r7fdmu9nk6nf2z32' THEN 'Valkyrie Staking'
              WHEN contract = 'terra1jxazgm67et0ce260kvrpfv50acuushpjsz2y0p' THEN 'bLUNA-LUNA Pair Terraswap'
              WHEN contract = 'terra12kzewegufqprmzl20nhsuwjjq6xu8t8ppzt30a' THEN 'Nexus PSI-UST LP Staking'
              WHEN contract = 'terra1g7jjjkt5uvkjeyhp8ecdz4e4hvtn83sud3tmh2' THEN 'Apollo Factory'
              WHEN contract = 'terra1fxwelge6mf5l6z0rjpylzcfq9w9tw2q7tewaf5' THEN 'Spectrum Staking'
              WHEN contract = 'terra1gm5p3ner9x9xpwugn9sp6gvhd0lwrtkyrecdn3' THEN 'ANC-UST Pair Terraswap'
              ELSE 'UNKNOWN' END as contractname, 
```
