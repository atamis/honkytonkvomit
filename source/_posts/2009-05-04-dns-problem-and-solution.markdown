--- 
layout: post
title: DNS Problem and Solution
wordpress_id: "140"
wordpress_url: http://geeklob.wordpress.com/?p=140
categories: Uncategorized
---
For some time, I have had a problem. My computer has failed, for some time, to aquire the proper DNS server from the wireless router. However, it only happens on some wireless networks. So, I signed up for OpenDNS, and I use it frequently. However, whenever my computer suspends, I lose my dns settings on these networks. So, I wrote a shell script to add OpenDNS to my DNS settings. The Script:

{% codeblock dns.sh %}
#!/bin/bash
echo Contents of /etc/resolv.conf:
cat /etc/resolv.conf
echo Replace dns with open dns, press enter. Otherwise, press ^C.
read $LFJLKJLKJSF
echo nameserver 208.67.222.222 > /etc/resolv.conf
echo nameserver 208.67.220.220 >> /etc/resolv.conf
echo Done. New contents of /etc/resolv.conf
cat /etc/resolv.conf
echo Happy?
{% endcodeblock %}

The first few lines prints out /etc/resolv.conf, and asks whether the file has open dns or not. If you press enter, it is given to a junk variable, and it continues. ^C to cancel. It then replaces /etc/resolv.conf with te first OpenDNS server, then adds the second. It then prints out the file to make sure, then exits. Rather useful.
