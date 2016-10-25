---
layout: post
title:  "The Internet Is Your Oyster"
date:   2016-10-23T20:12:00Z
categories:
---

The joy of pulling all nighters alone is that you are 100% productive, at least that is the effect it has on me. I tend to be more focused and produce quality code from the hours of midnight till nine in the morning. In addition, physically being in the 
gates dell building prevents me from straying off into the never ending depths of the internet, especially [Reddit][reddit] and [Twitch][twitch]. I just feel more compelled to be productive than I do at home. Perhaps, it is the fighting spirits of Bill Gates that pushes me towards completion.

During these all nighters, I remodeled the site to serve client side instead of server side. Previously, Flask was compiling the templates through Jinja and serving that to the client. Now Flask simply serve an one page app that is built client side through Angular. The main shift was delegating all routing logic to the routeProvider module. The provider has the ability to define parameters in the url, which helps with templating the individual items within the pillars, such as a food item under ingridents. Temaplates were pretty straight forward. You would feed some data through the `$scope` variable with either services or factoriess to the template and add some ng tags to render the proper data, `ng-href` or `ng-src` for exmaple. The ability to create templates in Agnular certainly saved a heck a lot of tedious work. You might have noticed I mentioned earlier to use either a service or factory, but to be quite honest, I do not know when the right situation is to use either one. Though here is a detailed StackOverflow [answer][which-one] to help you understand the difference between them.

While transitioning to majority client side work, I also modified the frontend too. Using bootstrap and some CSS magic, the site has some modern elements that caters to web applciations today. Most of the work, simliar to the backend code, were done through experiementing and, frankly, tons of googling. Going back to the title of the post, "The Internet is your Oyster", the whole world wide web is at your disposal. With the help of browser consoles, you can see network traffic, disable caching, and most importantly manipulate the DOM and CSS. If you see something interesting that a website implemented, go into their css and javascript and see what library they are using. Perhaps, it is open source and you can leverage that on your website! 

With the next project approaching, I am looking forward to exchanging roles with my teammates so everyone is better accomodated as well as learning new layers of the tech stack. Of course, lesson learned, we will start earlier this week to prevent these heart stopping final hours in the GDC from occuring. 

#### Tip of the Week
If you are working on frontend, [Chrome DevTools][chrome-dev] is your best friend. You can disable caching in the network tab. You can manipulate the DOM and CSS. You can change the screen size to emulate a desired device's screen. There are many more features the tool provides so go explore! To start, press `F12` for Windows or `Cmd + Opt + I` for Macs.

#### Helpful Links
[Bootstrap][bootstrap]

[Next Project][project-two]

[project-two]:		http://www.cs.utexas.edu/~fares/cs373f16/CS%20373_files/projects/IDB2.html
[bootstrap]:		https://getbootstrap.com/
[chrome-dev]:		https://developers.google.com/web/tools/chrome-devtools/
[reddit]:			https://www.reddit.com/
[twitch]:			https://www.twitch.tv/
[which-one]:		http://stackoverflow.com/questions/23074875/angularjs-factory-and-service