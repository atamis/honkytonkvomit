--- 
layout: post
title: Obscuring Information in Function Calls
wordpress_id: "188"
wordpress_url: http://geeklob.wordpress.com/?p=188
categories: Programing
---
While the usefulness of this is questionable, it is possible to obscure valid information in a bogus function call. Check out the following code:

[sourcecode language="ruby"]
class Example
	def new(*args)
		puts &quot;Got data: &quot; + args[1] if method_name == :new
	end
end
[/sourcecode]

You can then write the following code:

[sourcecode language="ruby"]
Example.new(&quot;127.0.0.1&quot;, 1342)
[/sourcecode]

And it should print out "127.0.0.1". What's more, the actual call looks like an internet connection, not something that might print something. Again, the usefulness of this is questionably, but it could be useful.
