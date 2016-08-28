---
layout: post
title:  "Here are lies the Markdown"
date:   2016-08-27 15:21:04 -0500
categories: playground templates
---
#### Ruby Code Snippet
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

#### Embedding an Image 
![Puppy]({{ site.url }}{{ site.baseurl }}/_assets/puppy.jpg)

#### Embedding a Link
Visit my [blog][blog-url]

#### Blocking text 
This is an `example` of a blocked text

[blog-url]:  https://wolfier.github.io/blog/