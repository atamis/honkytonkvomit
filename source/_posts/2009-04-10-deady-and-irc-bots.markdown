--- 
layout: post
title: Deady and irc bots.
wordpress_id: "133"
wordpress_url: http://geeklob.wordpress.com/?p=133
categories: Computers
---
I recently got involved in the creation of irc bots. It is common knowledge that my language of choice is ruby, so I set about making a bot in ruby. None of my friends had used ruby, they had used perl and PHP. I got an IRC library, and improved it, adding support for joining channels after the MOTD, a problem which was afflicting my bot (it wouldn't always join the channels) an added support of auto-joining mutliple channels. I am currently working on a weapons system and dice bag. I then forked the project, and created Deady, a hellish irc bot. Deady is just like my other IRC bot, only Deady is contained in a single file, which you can download <a title="Download Deady! The hellish IRC bot." href="http://http://www.box.net/shared/xm5ca2ftpa">here</a>. Deady utilzes ruby's random number generator to generate a random name. It then joins the specified channels, and sits, doing nothing. However, if somebody says:
`botsnack`

Deady will say: botsnack, starting a vicious cycle where each deady will say botsnack, causing the other one to say botsnack, and causing all the other bots in the channel to respond with thier proper botsnack response (typicaly ":D.") Though it has not been tested in a real world enviroment, I trust it works well. You can visit my nice bot, RBHellfire, on #bots on irc.foonetic.net. He doesn't do much yet.

-Indigo
