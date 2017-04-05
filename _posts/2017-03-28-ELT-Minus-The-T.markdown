---
layout: post
title:  "ELT minus the T"
date:   2017-03-28T16:18:40Z
categories:
---

This semester I got the chance to proctor a database course taught by [Shirley Cohen][cohen-linkedin]. The goal is to educate non-computer science students the basics of databases and data warehousing. For their final project, the students were tasked with building a data warehouse from a couple of music related data dumps from [Musicbrainz][mb], [Million Songs][ms], and [Discog][dc]. As the proctor, I am tasked with performing the EL part of the ELT to ensure proper format for copying and foresee any problems students might have when loading into Redshift.

I was tasked with preprocessing the [Musicbrainz datadump][mb-dump] and the [Discog datadump][dc-dump]. Let's start with Discog because that was the one I couldn't figure out. Discog stored their dumps as XML, a format that I cannot load with Redshift's copy command as is. I need to convert the XML to CSV for that to happen. After experimenting with many tools and scripts, I just couldn't manage to make a proper transform without having to write an XLD schema. Sean, the other proctor, managed to write a script to end my miseries in the end. Next, we move on to the Musicbrainz tables, which also had its own issues. Upon inspecting the data, I saw that the files are tab delimited and the nulls are denoted by `\N`. My first approach involved writing a python script that will read every single line and replace the tabs with commas. Due to the size of these tables, ranging from 10MB to 3GB, python is unable to keep them all in memory for the replace. So instead I just read in the csv as is with the named argument `delimiter` set to `\t` for tabs and simply write it out since the default value for delimiter is comma.
```
in_txt = csv.reader(i, delimiter = '\t')
out_csv = csv.writer(o)
```
After a quick glance at the tables, everything seems to be in order for loading into Redshift!

The loading process was pretty straight forward. When Redshift runs into a bad record though, it was sort of tedious to debug. I needed to query the error from the stl_load_errors table, which thank god has the reason for error and the line number of the offending record. However, even with the line number, opening a large file is difficult and unnessary since I only need to know the content of that one line. So to counter that bottleneck, I used sed, a unix utility tool, to do exactly that without loading the whole file.
```
sed ‘<line number>q;d' <file>
```
Once I identified the error, I remade the table with the correct type and reloaded again. That was until I ran into the `Extra column(s) found` error. I ran into something like below. 
```
14932,sam,two island,9,1,1,,0
14933,hallow,"Something	10	1	1	4
...
15391, samption, Dave	10	1	1	0
15392, golle, Jillian	8	1	1
...
15811	he	Hed",10,1,1,3
15812,jae,Jane,10,0,1,1
```
It took me a while to realize that the csv reader recognizes `"` as the quotechar by default. With a little more research, I found out that setting the quoting argument, which by default is `csv.QUOTE_MINIMAL`, to `csv.QUOTE_NONE` will treat quote characters as regular text. 
```
in_txt = csv.reader(i, delimiter = '\t', quoting = csv.QUOTE_NONE)
```
I ran the script again and doubled checked around that range. Everything seems good. Now that's sorted out, I tried to load the data again, hopefully for the last time. After a few minutes, I got the number of rows it uploaded meaning **IT WORKED**! 

As as sidenote, I realized that the copy command has a delimiter option. I could have done without converting the tabs to commas and not have ran into the whole fiasco in the first place. This only reinfornces the age old saying of [RTFM][rtfm] or read the fucking manual.


[cohen-linkedin]:	https://www.linkedin.com/in/shirleycohen/
[psql]:				https://www.postgresql.org/docs/9.2/static/app-psql.html
[rs]:				https://aws.amazon.com/redshift/
[mb]:				https://musicbrainz.org/
[ms]:				https://labrosa.ee.columbia.edu/millionsong/
[dc]:				https://www.discogs.com/
[mb-dump]:			https://musicbrainz.org/doc/MusicBrainz_Database/Download
[dc-dump]:			http://data.discogs.com/?prefix=data/2017/
[rtfm]:				https://en.wikipedia.org/wiki/RTFM
