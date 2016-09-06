---
layout: post
title:  "On the Brink of Collatz"
date:   2016-09-06 13:24:00 -0500
categories: swe collatz
---

As the past week went by in a flash, I accomplished the impossible. The joyous moment when I saw "accepted" in white underneath the black pit of darkness that is [Sphere][sphere-problem], I shed one tear. One that is very manly liquid tear. Of course, I took the liberty to screenshot what is comparable to a trophy to me at this point. 

![And it did, eventually]({{ site.baseurl }}/assets/sphere_ac.png)

As the age old [adage][adage-home] goes, 

>This too shall pass.

You couldn't imagine what I went through to get those words to appear on my screen. I tried various optimizations: recursion, lazy and eager caching, limiting the range of calculation, and bitwise operators. BUT none of them worked or so I thought. "TLE, Time Limit Exceeded" or "NZEC, Non-Zero Exit Code" are what returned with each submission...and each time my heart breaks a little. I really wish they provided better outputs but that defeats the purpose of the online judge. In the end, my submission was finally accepted due to something I think is trivial and unconsequential to have. I simply switched my loop to run from low to high and that for reason solved my issue... 

Putting aside the grueling task that is solving the optimization problem, Github and Travis-CI on the other hand stayed on my good side. Setup wasn't complicated and was fairly straight forward. I am really impressed with how well Travis is integrated with Github, especially the feature of the project automatically building whenever a branch is pushed. There were some miscommunication, however, when I was following the steps on the [project page][assignment-link]. For exmaple, Step 14 specified to copy the "code files" but really only the files in collatz were needed. What made matters even more confusing was that there existed already a makefile in the root folder in the cloned repo with similar targets. Even though there are already 40 steps in the requirements, there could have been more precise and clear instructions. I do understand life in the world is not that simple so take my greviances with a grain of salt. 

As I was doing the project and reading the questions of my classmates, makefiles seem to be a mystery to the majority. Makefiles abstract away the commands in the sense that it compacts them into one target that lets you set depencies for that target. A big misconception is what the errors generated when make fails mean. An typical error looks like `make: *** [TestCollatz.tmp] Error 127`. This tells us a non-zero exit code was recieved. However, MAKE DOES NOT HAVE EXIT CODES or more specifically the exit codes are not from make but rather from the line that make last ran. So next time when you have a make issue, try following these steps.

1) Determine the line that exited with a non-zero code

2) Google something along the lines of "[command] exit code [the non-zero code]"

Given I finished the project, I will try my best to help my classmates and answer questions diligently on pizza. I hear some people are just now starting the project, perhaps to take advantage of those who finished or to maybe this is what working smart means. Other than finishing up some readings, I will continue looking over class material along the week.

#### Tip of the Week
Since the career fair is coming up and recruiting season is among us, I thought this [article][tip-link] will help with evaluating offers to companies that will you developing software for. 

Stolen shamelessly from Jon Lee in the Computer Science Group.

#### Helpful Links for the Project
[Project page][assignment-link]

[Collatz output generator][output-generator]

[Collatz calculator][collatz-solver]

[More on cprofile][cprofile-help]

[Line graph for Collatz][collatz-graph]

[tip-link]: https://blogs.janestreet.com/unraveling/
[output-generator]: http://www.uvatoolkit.com/problemssolve.php
[collatz-solver]: http://www.nitrxgen.net/collatz/10/
[cprofile-help]: https://ymichael.com/2014/03/08/profiling-python-with-cprofile.html
[collatz-graph]: https://skanderkort.com/collatz_conjecture_calculator
[sphere-problem]: http://www.spoj.com/problems/PROBTNPO/
[adage-home]: https://en.wikipedia.org/wiki/Adage
[assignment-link]: http://www.cs.utexas.edu/~fares/cs373f16/CS%20373_files/projects/Collatz.html
