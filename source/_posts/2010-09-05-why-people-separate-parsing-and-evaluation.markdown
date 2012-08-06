--- 
layout: post
title: Why people separate parsing and evaluation
wordpress_id: "264"
wordpress_url: http://geeklob.wordpress.com/2010/09/05/why-people-separate-parsing-and-evaluation/
categories: code
tags: [ruby, code, esolang]
---
I forget if I have announced it here, but I've got a small, crappy language called Rorth, which you can find on my github site (link on my software page.) I say crappy because it can't handle nested blocks. Thats right, you can write an if inside a while, or anything like that. So I've set off on a quest to rewrite the rorth parser from scratch. I've been playing around with the recursive decent parsers people have posted on the internet for use, and they work fairly well. However, I wanted to write my own, so I started. I've learned about solid state automaton since I wrote the first parser, so this one looks pretty different. I hadn't wanted to write too much code, so I implemented parsing and evaluation in one step. This turns out to be just fine if you have an if statement, and possibly a function declaration though I haven't gotten to that part yet, but for while, it breaks down. It has to do with storing the code in the while block for later use, and identifying when a while block ends. So, I've learned that one does not place parsing and evaluation in the same step. So, no new parser for Rorth yet.
