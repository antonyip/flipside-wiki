---
description: 'Credits: lambdadelta#7856'
---

# QUERY - Liquidity Pools

```
CASE
 
    WHEN column_here = 'terra106a00unep7pvwvcck4wylt4fffjhgkf9a0u6eu' THEN 'loop-ust'
    WHEN column_here = 'terra1sgu6yca6yjk0a34l86u6ju4apjcd6refwuhgzv' THEN 'luna-ust'
    WHEN column_here = 'terra17pzt8t2hmx6587zn6yh5ensylm3s9mm4m72v2n' THEN 'halo-ust'
    WHEN column_here = 'terra1dw5j23l6nwge69z0enemutfmyc93c36aqnzjj5' THEN 'loopr-ust'
    WHEN column_here = 'terra1jfp5ew4tsru98wthajsqegtzaxt49ty4z2qws0' THEN 'twd-ust'
    WHEN column_here = 'terra1jkr0ef9fpghdru38ht70ds6jfldprgttw6xlek' THEN 'spec-ust'
    WHEN column_here = 'terra1cpzkckgzz90pq8fkumdjc58ee5llrxt2yka9fp' THEN 'mir-ust'
    WHEN column_here = 'terra1lgazu0ltsxm3ayellqa2mhnhlvgx3hevkqeqy2' THEN 'stt-ust'
    WHEN column_here = 'terra13eggta6zqfg03mxgqg9p5paqka7tgaaxnkhuuu' THEN 'mine-ust'
    WHEN column_here = 'terra1f6d3pggq7h2y7jrgwxp3xh08yhvj8znalql87h' THEN 'anc-ust'
    WHEN column_here = 'terra15568nqrqcawm263yqcuuuvj5mh763tp8jyscq3' THEN 'lota-ust'
    WHEN column_here = 'terra1whns5nyc8sw328uw3qqnyafxd5yfqsytkdkgqz' THEN 'alte-ust'
    WHEN column_here = 'terra178yhudw6cwtnrn4fq593z87y385m0xe9n6x423' THEN 'dph-ust'
    WHEN column_here = 'terra1wh2jqjkagzyd3yl4sddlapy45ry808xe80fchh' THEN 'kuji-ust'
    WHEN column_here = 'terra17e0aslpj3rrt62gwh7utj3fayas4h8dl3y8ju3' THEN 'wewbtc-ust'
    WHEN column_here = 'terra17kmgn775v2y9m35gunn3pnw8s2ggv6h95wvkxr' THEN 'weweth-ust'
    WHEN column_here = 'terra1fgc8tmys2kxzyl39k3gtgw9dlxxuhlqux7k38e' THEN 'wewbtc-luna'
    WHEN column_here = 'terra1pmmfz205es7axymwpl4jj2ruxnevufu3462f02' THEN 'weweth-luna'
    WHEN column_here = 'terra1v93ll6kqp33unukuwls3pslquehnazudu653au' THEN 'bluna-luna'
    WHEN column_here = 'terra18r6rdnkgrg74zew3d8l9nhk0m4xanpeukw3e20' THEN 'bluna-ust'
    WHEN column_here = 'terra1me6a35xuzf9ycjaaqyj7798g5tewunp6dzg27e' THEN 'whmim-ust'
    WHEN column_here = 'terra123neekasfmvcs4wa70cgw3j3uvwzqacdz2we03' THEN 'aust-ust'
    WHEN column_here = 'terra15xxfkxldxse9atz8ce7ne2a047pp09dy428njm' THEN 'anc-aust'
    WHEN column_here = 'terra16j5f4lp4z8dddm3rhyw8stwrktyhcsc8ll6xtt' THEN 'luna-aust'
    WHEN column_here = 'terra1l60336rkawujnwk7lgfq5u0s684r99p3y8hx65' THEN 'kuji-aust'
    WHEN column_here = 'terra1x4msd26x8ncqcng3dapx8306rmgwuwtlg30a2j' THEN 'loop-weweth'
    WHEN column_here = 'terra154jt8ppucvvakvqa5fyfjdflsu6v83j4ckjfq3' THEN 'loop-loopr'
    WHEN column_here = 'terra1tus5ec9qsdht8dapq9ldfnsf8eehnfmwvsut83' THEN 'luna-loop'
    WHEN column_here = 'terra1kw95x0l3qw5y7jw3j0h3fy83y56rj68wd8w7rc' THEN 'loop-lota'
    WHEN column_here = 'terra13ay3hftcft25uazl76q8gmdk993y9nyv9avu2h' THEN 'loop-mir'
    WHEN column_here = 'terra1w7hny2catfwsv6dq8gfm4zgazx3hmpl3xwzxya' THEN 'loop-anc'
    WHEN column_here = 'terra1a26j00ywq0llvms707hqycwlkl9erwhacr6jve' THEN 'loop-mine'
    WHEN column_here = 'terra1tksv8cn7j95mecxjhj3dgcz3xtylcw5xkarre7' THEN 'loop-wewbtc'
    WHEN column_here = 'terra1tus5ec9qsdht8dapq9ldfnsf8eehnfmwvsut83' THEN 'loop-luna'
    WHEN column_here = 'terra10s94a5gesvayqlekgn570r3nsnmr8q7lf5zkjp' THEN 'loop-whmim'
    WHEN column_here = 'terra12aazc56hv7aj2fcvmhuxve0l4pmayhpn794m0p' THEN 'loop-halo'
    WHEN column_here = 'terra1efvhm927dehrka0cgpcptt5gvjfdgqm07smawu' THEN 'loop-aust'
    WHEN column_here = 'terra13f87x4c87ct5545t3j4mqw4k6jmgds5609z92c' THEN 'loop-kuji'
    ELSE NULL
 
END
```
