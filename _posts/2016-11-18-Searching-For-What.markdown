---
layout: post
title:  "Searching For What"
date:   2016-11-18T01:29:00Z
categories:
---

The last stage of our project is finally completed! You are now able to search through our database for cuisines, recipes, and ingredients on the [Boilerpl8][foods] landing page. The search function is modelled like a suggestion dropdown, where it will display the most relevant items according to your input. Part of the requirement asked for both `AND` and `OR` queries, which I thought was odd at first. After some thoughts, it made sense. If there aren't any good matches, you still want to show the user somewhat related searches with looser restraints.

For the dropdown listview, I wrote a custom Angular directive that would call our search endpoint, which returns a JSON of related items given a query and limit, if the time between the key presses is less than 200 milliseconds. You might be wondering why I took that approach even though there are plenty of modules that are out there on the internet. Well, you see, I am more interested in learning Angular than taking a shortcut where I don't code anything myself. On the other hand, using those modules as examples and dissecting how they implemented is the perfect approach for learning in my opinion. Reverse engineering forces you to not be contempt with a black box, where you have no idea what lays under the abstraction.

Even though we did a great job updating the landing page design and functionality, we forgot to update the log file that contains our commits. It is unfortunate that a single mistake could have such a big impact on our grades. However, in the real world, a small mistake like that could incur a much greater cost. It was a small price to pay to learn an important lesson. 

Overall, the project was the most enjoyable and valuable part of the course. I gained lots of experience of and motivation for making my own website using these new technologies and methodologies. However, I wished professor Fraij had incorporated agile methodology better. For starters, the user stories and sprint planning should have been done at the beginning of each stage, so each group has a better understanding of what needs to be done. Also, each group should meet with the clients, who in this case are the TAs, to discuss the progress of the product, which is what would happen at a company. 

#### Tip of the Week
While it is important to be an innovator, don't forget to draw inspiration from others. Get out there and see what people have done and perhaps incorporate them into your own developement process. 

[foods]:	http://boilerpl8.me 