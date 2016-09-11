---
layout: post
title:  "Netflix and Panic"
date:   2016-09-11 12:09:00 -0500
categories:
---

Despite finishing the project a week ago and double checking my work, I still received a Canvas message from one of the TAs about failing tests on a Friday night of all nights. I panicked. Scenarios raced through my mind. What could have failed? What did I overlook carelessly? Nothing came to mind. I had submitted my tests to the public repo. I had made sure `make test` returned a zero exit code on my machine, the lab machine, and Travis CI. Thank goodness I check my emails frequently to notice the message, otherwise I would have to suffer penalties because the grader will not grade given that there are missing files. The Canvas message referred to a Piazza post about uncommenting public test files in the makefile, which I followed through and made appropriate changes. Why those lines were uncommented is beyond me. I certainly hope I do not receive a bad grade because of this overlook. 

I have a couple of complaints about how the first project was managed after going through this experience. 

* TAs should clarify submission details at the release of the project, not the day of submission.
* Lines that determines whether the submission is valid should not be commented out.
* Points should not be deducted due to this error, because my tests were in the public test repo as outline in the project page.

Putting the whole Collatz fiasco behind me, I looked into the next [project][netflix-project] titled 'Netflix'. I noticed we are able to pick partners on this assignment, which I am very happy about! Having a second pair of eyes really improves the quality of code and reduces the amount of bugs and blindspots. I hope future projects gives us the option to work in teams as well because this class is suppose to give us experiences as close to real world as possible. Team work is essential in the workplace as I have noticed in past internships. It is something that is highly coveted in a communicative profession. You need to be able to convey your idea in writing and to each other without accidentally creating pitfalls and misunderstandings. Project content wise, I think I understand what we are suppose to do but the question is how we can do it. There also seems to be missing links to the codebase on the project page. However, I anticipate all these questions will be answered in the next class.

#### Tip of the Week
Do you want to autopep8 on the fly? There is a [Sublime package][pep-link] that lets you do that! 

#### Helpful Links for the Project

[Understanding the Netflix Prize][netflix-overview]

[netflix-project]:	http://www.cs.utexas.edu/~fares/cs373f16/CS%20373_files/projects/Netflix.html
[netflix-overview]: http://blog.echen.me/2011/10/24/winning-the-netflix-prize-a-summary/
[pep-link]:			https://github.com/hhatto/autopep8


