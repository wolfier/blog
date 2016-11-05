---
layout: post
title:  "Database, We Have A Problem"
date:   2016-11-04T10:14:00Z
categories:
---

We did it again...it being that we waited until the last possible minute to submit the project. However, we did have a good reason this time. While we were inserting into our database, we realized not every recipe has the same amount of an ingredient. For example, orange cake requires one cup of whole milk but chocolate cake needs only one-half cup. It does not make sense to have an attribute that relates directly to the recipe in the ingredient model. But it doesn't belong in the recipe either because there is one measurement for each ingredient. The solution was to create an ingredientInfo model that contains data such as measurement(one cup, six teaspoons, etc.), descriptor(thinly sliced, peeled, etc), and a relational link that connects to the described ingredient.

Aside from the *small* hiccup, the rest of the project went by pretty smoothly. Though there was a scary moment before the submission time. The WSGI file appended the wrong absolute path in the python instance. So when we restarted the server, we got the worse possible error, `ImportError: No module named models`. Models are the backbone of the entire web application! It took a bit of searching but once we figured out it was the bad path int he WSGI file, everything worked as expected. 

There are a few new features implemented this iteration. Linkage between cuisine, recipes, and ingredients, are one of them. You can move from **5 Spice Cajun Shrimp** to either the **Cajun** cuisine page or any of the pages of the ingredients involved, say **shrimp**. Another feature is running unit tests for the database. Our tests assure that you can perform basic CRUD operations on the models.

Now after making this database focused application, I am inspired to build my own web page from scratch using the very same technology. Before, I paid for a web hosting service that had very little customization or control. With full access of digital ocean droplets, I am able to do much much more.

#### Tip of the Week
I am not sure on how I can survive without the help of the internet (there's always books I suppose, but think about the paper). All these online resources are available to me at a click of a button. To help you find these resources, you should learn these [search operators][search] for google search and take a look at this [guide][smart-google] on effective googling.

#### Helpful Links
With Stage Three coming up, you should start thinking about what other student-made website you want to incorporate. Here are the websites available.

[Boilerpl8][Boilerpl8]

[Litdb][Litdb]

[Video Game Character DB][VGDB]

[iMusicDB][iMusicDB]

[PokemonDB][PokemonDB]

[ResearchPapersDB][ResearchPapersDB]

[BestBytes][BestBytes]

[search]: 					https://support.google.com/websearch/answer/2466433?hl=en
[smart-google]:				https://d3rgj9au57pk8c.cloudfront.net/uploaded/attachments/11080.gif
[Boilerpl8]:				http://www.boilerpl8.me/
[Litdb]:					http://litdb.me/
[VGDB]:						http://vgidb.me/
[iMusicDB]:					http://www.imusicdb.me/
[PokemonDB]:				http://www.pokemans.me/
[ResearchPapersDB]:			http://researchpapers.me/
[BestBytes]:				http://www.bestbytes.me/