--- 
layout: post
title: "Bitcoin as a currency and benchmark"
wordpress_id: "298"
wordpress_url: http://geeklob.wordpress.com/?p=298
categories: misc
tags: [bitcoin, mac, linux]
---
I recently discovered Bitcoin, and I've been running it on my laptop for some time, hoping to get luck. I haven't, of course, and my wealth consists of 0.04 bitcoins. I got 0.05 from the Bitcoin Faucet, and lost 0.01 to transaction fees. I have, however, joined a mining pool called <a href="mining.bitcoin.cz">mining.bitcoin.cz</a>. I've got it running on my server and my iMac, but my laptop has a bad overheating problem, and I fear that running the miner for too long would cause it to shutdown. I have successfully used <a href="http://www.bitcoin.org/smf/index.php?topic=1925.0">cpuminer</a>, but it was hell to compile on my mac. I had to steal a functional bitswap.h from OpenGL, and the bleeding edge wouldn't compile due to, as far as I can tell, autoconfig issues. It compiled fine on my linux laptop and server, and I've got it running on my iMac and server. CPUMiner reports khash/sec regularly, so I can now say that my iMac is 4 times faster than my server, and my laptop is 5 times faster. Sadly, due to other, unsolved, compilation issues, I can't take advantage of the GPU in my iMac, so I suspect that in raw power, my iMac actually wins the race, but I haven't gotten a combination CPU/GPU miner running yet. I haven't seen any payoff yet, so let's hope I haven't messed something up, and I am, in fact, contributing to the mining pool.
