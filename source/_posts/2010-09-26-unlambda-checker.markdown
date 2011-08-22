--- 
layout: post
title: Unlambda Checker
wordpress_id: "266"
wordpress_url: http://geeklob.wordpress.com/?p=266
categories: Uncategorized
---
Been looking at Unlambda. and it's website offers a simple algorithm for determining whether or not a string is a valid Unlambda program
[sourcecode language="ruby"]
def unlambda_checker(input)
     counter = 0
     input.split(//).each { |x| x == '`' ? counter += 1 : counter -= 1 }
     counter == 0
end
[/sourcecode]
This has undergone rudimentary testing

</div>
