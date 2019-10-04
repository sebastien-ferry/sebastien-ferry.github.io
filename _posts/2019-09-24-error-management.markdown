---
layout: post
title:  "Error management"
date:   2019-09-24 12:35:28 +0800
categories: [blog, coding]
tags: [python, error]
excerpt_separator: <!--more-->
---

I made a habit at work to structure my programs around an error management backbone.

For business, it is critical to ensure that all errors are caught and handled, with critical ones getting proper feedback to user.

That applies to serious business.
<!--more-->
## Dr Jekyll and Mr Hyde
## Work/robust coding VS fun coding

But sometimes it is overkill:
  * Adding error management adds complexity. And a simple script of 10 lines becomes a fat one of 50-80 lines.
  * Logging may generate errors!
  * Error inside error management functions are also a thing...
  * Handling all errors may require a lot of effort, for error that will almost never happen (config missing or else)

All in all, a nice crash when acceptable may bring as much information.
In this case, error is managed by the upper layer (the operating system), and life goes on...


{% highlight python %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}
