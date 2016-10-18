---
layout: post
title:  "Drowning in the Digital Ocean"
date:   2016-10-17T22:18:00Z
categories:
---

That moment when you think you understand what is happening when you are reading a tutorial but not actually doing the steps hits hard during this project. Team Boilerpl8 (that's right, we cool cause leetspeak) and I spent the first week reading over the tools and documentations, imagining the setup to be straightforward and quick given Bryan's guide on spinning a Digital Ocean server. However, that was not the case. When is that ever the case... 

Just this past weekend, we expected everything to run smoothly. We followed the guidelines and setup everything that was needed, the apache server, flask, wsgi, and the config files. But this was where it all goes horribly and exhaustingly wrong. When we reached the end of the tutorial, we restarted the apache service hoping to see our index endpoint. We did not see that. Instead, we saw the default index.html congratulating us on correctly setting up the apache service. It took us an hour or two for us to realize to consult the apache error.log for guidance. There it contains the worst possible sentence, `No module named flask`. These words haunted my dreams and gave my nightmares nightmares. We tried countless suggested solution but to no avail. In the end we decided to scrap the droplet and spin up a new one.

After a few links deep into Google. I discovered that the `libapache2-mod-wsgi` package hat Bryan had us install runs on python 2.7. However, the python alias maps to 3.5 not 2.7. To be consistent, we need to install `libapache2-mod-wsgi-py3` package to comply with the version of python we have and all following modules needed to be ran as a script under version 3.5 to be safe. And this was just one of the two big pain points in setting up the flask server on apache.

Now we have all complying modules under python 3.5, python can find the flask module and its various imports, AMEN. You would imagine that was it, but as you can guess, that, unfortunately, wasn't the end of it. Everything works...besides port 80. The apache server still rendered the default apache congratulations page and not the proper flask endpoints. Again, after a variety of google searches and depth first searching the links, we found that we need to disable the default config with:

{% highlight bash %}
a2dissite 000-default.conf
{% endhighlight bash %}

which I imagined had priority thus taking over our project config. I prayed and hoped when I ran:

{% highlight bash %}
service apache2 restart
{% endhighlight bash %}

And there it was, `Hello World`, right in front of my eyes. Those were the most beautiful words I have ever seen. I might have even shed a tear.

With a working flask server, all we need now are some static HTMLs with data from the API service we found. We are waiting on free access from the developers, but we still have 50 calls to the API, which is enough to help us fill the static pages. With the next [phase][phase-two], we are converting the existing pages to be served dynamically. But before we get ahead of ourselves, the team and I will satisfy the requirements and make everything extra hip.

#### Tip of the Week
Given that we are in a Software Engineering course, I thought it would be a good idea to follow the common 4-tier architecture, development, testing, staging, production (DEV, TEST, STAGE, PROD). You can read more about it [here][deployment-architecture].

#### Helpful Links
[Understanding mod_wsgi][mod-wsgi]

[Setup Python3 and Apache2 on Ubuntu][deploy-flask]

[Github Wiki Code Color Scheme][wiki-code-highlight]

[Bryan's Digital Ocean Setup Guide][bryan-setup]

[Github Wiki Exmaple - D3][d3-wiki]


[phase-two]:			http://www.cs.utexas.edu/~fares/cs373f16/CS%20373_files/projects/IDB2.html
[deployment-architecture]:	https://en.wikipedia.org/wiki/Deployment_environment
[mod-wsgi]: 			http://flask.pocoo.org/docs/0.11/deploying/mod_wsgi/
[deploy-flask]:			http://terokarvinen.com/2016/deploy-flask-python3-on-apache2-ubuntu
[wiki-code-highlight]:	https://highlightjs.org/static/demo/
[bryan-setup]:			https://github.com/brpowell/flask-example/wiki/Hosting-on-Digital-Ocean
[d3-wiki]:				https://github.com/d3/d3/wiki
