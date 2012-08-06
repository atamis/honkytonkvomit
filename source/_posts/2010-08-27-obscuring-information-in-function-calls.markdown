--- 
layout: post
title: Obscuring Information in Function Calls
wordpress_id: "188"
wordpress_url: http://geeklob.wordpress.com/?p=188
categories: code
tags: [code, ruby, stupid]
---
While the usefulness of this is questionable, it is possible to obscure valid information in a bogus function call. Check out the following code:

```
class Example
	def new(*args)
		puts "Got data: " + args[1] if method_name == :new
	end
end
```

You can then write the following code:

```
Example.new("127.0.0.1", 1342)
```

And it should print out "127.0.0.1". What's more, the actual call looks like an internet connection, not something that might print something. Again, the usefulness of this is questionably, but it could be useful.
