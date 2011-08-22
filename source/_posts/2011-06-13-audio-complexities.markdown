--- 
layout: post
title: Audio Complexities
wordpress_id: "309"
wordpress_url: http://geeklob.wordpress.com/?p=309
categories: Uncategorized
---
I have 2 computers that I like to use simultaneously. I have  sets of headphones. I used to solve this problem by giving each computer its own set of headphones. When I needed to listen to something, I'd put on the appropriate headphones and listen. This worked pretty well.

In an attempt to play music into voice chat, I decided I would use 2 computers, because keeping it all contained on one computer wasn't working. So I used a male-male 1/8th inch audio jack to route the audio out from my laptop to the audio in on my desktop. Now I could play music, but when playing music I couldn't talk at the same time. This would require a little more complex internal routing. When routing audio around on a Mac, I have found <a href="http://cycling74.com/products/soundflower/" target="_blank">Soundflower</a> by Cycling 74 and <a href="http://www.rogueamoeba.com/freebies/" target="_blank">LineIn</a> (<a href="http://www.rogueamoeba.com/freebies/download/LineIn.dmg" target="_blank">download</a>) by Rouge Amoeba invaluable. Soundflower provides a virtual audio input/output on the mac. Any sound sent to Soundflower will be sent out Soundflower's output. LineIn allows you to route the output of one source to the input of another. You could, say, play the built in microphone of the computer through your headphones. LineIn can only do one route at a time, so I made several copies of the application so that I could set up several routings. You can now route your microphone and the laptop to Soundflower, route the laptop to your headphones, and have the voice chat take input from Soundflower. You can hear both computers, and the voice chat can hear your mic and the laptop.
