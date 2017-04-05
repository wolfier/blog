---
layout: post
title:  "ELT minus the T"
date:   2017-03-28T16:18:40Z
categories:
---

This semester I got the chance to proctor a database course taught by [Shirley Cohen][cohen-linkedin]. The goal is to educate non-computer science students the basics of databases and data warehousing. For their final project, the students were tasked with building a data warehouse from a couple of music related datadumps from [Musicbrainz][mb], [Million Songs][ms], and [Discog][dc]. As the proctor, I am tasked with performing the EL part of the ELT to ensure proper format for copying and foresee any problems students might have when loading into Redshift.

I was tasked with preprocessing the [Musicbrainz datadump][mb-dump] and the [Discog datadump][dc-dump]. Let's start with Discog because that was the one I couldn't figure out. Discog stored their dumps as xm, a format that I cannot load with Redshift's copy command as is. I need to convert the xml to csv for that to happen. After experimeting with many tools and scripts, I just couldn't manage to make a proper transform without having to write a xld schema. Sean, the other proctor, managed to write a script to end my miseries in the end. Next, we move on to the Musicbrainz tables, which also had its own issues. Upon inspecting the data, I saw that the files are tab delimited and the nulls are denoted by '\N'. My first approach involved writing a python script that will read every single line and replace the tabs with commas to conform to  


We used psql as an interface to interact with [PostgreSQL][psql] and [Redshift][rs]. 


The database  databases were [Musicbrainz][mb-dump]


[cohen-linkedin]:	https://www.linkedin.com/in/shirleycohen/
[psql]:				https://www.postgresql.org/docs/9.2/static/app-psql.html
[rs]:				https://aws.amazon.com/redshift/
[mb]:				https://musicbrainz.org/
[ms]:				https://labrosa.ee.columbia.edu/millionsong/
[dc]:				https://www.discogs.com/
[mb-dump]:			https://musicbrainz.org/doc/MusicBrainz_Database/Download
[dc-dump]:			http://data.discogs.com/?prefix=data/2017/


