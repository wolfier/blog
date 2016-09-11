---
layout: post
title:  "First build then serve"
date:   2016-08-27 16:18:40 -0500
categories:
---

Prior to the first day of class, I did some research into what this course consisted of in the past semesters, mainly to see if there was any exams if I must be frank. However, [Professor Fraij][fraij-link] had not taught Software Engineering at UT before, only Algorithms. Anyhow I have heard some good reviews and some not so good reviews regarding his lecturing style. After attending his lecture for the first time, I noticed some monotonal speech pattern the students mentioned, though it was a positive experience overall. I'm sure as the semester goes on, we will warm up to him and hopefully the same for Professor Fraij too with us.

We visited the [Collatz Conjecture][collatz-wiki] in the first lecture. The math itself wasn't terribly confusing. Anyone with basic mathmathics skills can understand the procedure. It can be summed up with the following python snippet.
{% highlight python %}
while n > 1 :
    if (n % 2) == 0 :
        n = (n // 2)
    else :
        n = (3 * n) + 1
{% endhighlight python %}
Essentially, given any positive integer, it will eventually converge at one if the process is repeated indefintely. The topic of `cycle length` came up, which was thoroughly explained with some in class exercises. I do wish some sort of graphical interpretation was drawn to help bridge the concept of optimization through caching. After some thorough searching, I found a few fairly interesting representations of the Collatz Conjecture, noteably this [cyclone shaped graph][collatz-graph].

While the Collatz Conjecture is interesting, I didn't really understand at first what this had to do with Software Engineering. It became apparent when I read through Project ones's specifications. I think this project's main goal is get the student to become acqainted with the tools that is used in the industury, inlcuding `Git` and `Travis CI`. Though I have dealt with git before this class, I have never heard of Travis CI and know very little beind the concept of continuous integration. I will need to do some documentation reading (pray that the docuemention doesn't suck) and make some progess on the project.

On the flip side, I really am enjoying the extra credit of this course. Self reflection and expression through prose are great ways to help students like me process the material and further solidfy the concepts in ours minds. [Setting up Github Pages][gh-url] and [installing Jekyll][jekyll-url] were pretty straight forward so I recommand other students to try it out. Though I do have to point out, [setting up Google Analytics][ga-url] took some googling but wasn't too bad in the end.

#### Tip of the Week
> Programs must be written for people to read, and only incidentally for machines to execute.

Quoted from the preface of [Structure and Interpretation of Computer Programs][book-url]


[fraij-link]: 		https://www.linkedin.com/in/fares-fraij-1b512929
[collatz-wiki]: 	https://en.wikipedia.org/wiki/Collatz_conjecture
[collatz-graph]: 	http://swimmingthestyx.com/wp-content/uploads/2014/01/CollatzTree_100000.png
[gh-url]: 			https://pages.github.com/
[jekyll-url]: 		https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/
[book-url]: 		https://mitpress.mit.edu/sicp/full-text/book/book-Z-H-7.html
[ga-url]:			https://desiredpersona.com/google-analytics-jekyll/

