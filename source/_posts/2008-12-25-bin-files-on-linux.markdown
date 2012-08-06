--- 
layout: post
title: .bin files on Linux
wordpress_id: "90"
wordpress_url: http://geeklob.wordpress.com/?p=90
categories: linux
tags: [code, shell, stupid]
---
Merry Christmas!

As you  may know, I got the acer back today, and I installed linux, ubuntu to be exact, and I needed to install java. It came in .bin file type, and ubuntu hadn't a clue what to do with it. Now, once, when I was downloading java, I accidentally viewed it as a text file instead of downloading it. Well, the first part I recognized as a bash script. Following the bash script, was some inane gibberish. Now, what do you do to this? Well, first, we know it's a script, but it doesn't have the permissions to run it. So, we have to use chmod. It doesn't matter what the permissions you put on it, as long as you can exicute it. My favorite is:

` chmod 711 ...`

This enables you to read write, and exicute, but everybody else can only read. Next, we have to go into the terminal. Navigate to where you have the .bin file, and type:

`./[the .bin file]`

In the case of the java file, you are presented with a long license. You should probably read this. After that, the ask you to agree to the liscense. After that, when you say yes, it will do what it takes to place the archive in the folder. Done

-Indigo

<em>edit: it turns out that these are called "self extracting archives." I didn't know this at the creation of the article/</em>
