---
title:  "Bad Data Management: A Star Wars Story"
authors:
- admin
date:   2020-02-01 10:50:02 -0700
draft: true
featured: false
diagram: true
image:
  caption: []
  placement: 1
projects: []
categories: []
tags: 
- data workflow 

---

Most of us think of Star Wars as the rebellion versus the empire -- good versus evil with key figures: the Jedi, the Sith, Darth Vader, Luke Skywalker, the Emperor, Rey, Kylo Ren. But, The downfall of the governing bodies was not Darth Vader, Luke Skywalker, Kylo Ren or Palpatine. Actually, Star Wars is a story of really bad data management practices.  

#### The Republic:

The Jedi maintained decent, well-organised archives in a large library and they even had paid librarians on staff. But any jedi can delete information and no record is left regarding this? For heaven’s sake, an entire planet was removed from said archives That ain’t good. It led to the Clone wars and eventual rise of the Galactic Empire. It also turns out that a person just has to look like a jedi in order [to steal secured jedi archives](https://starwars.fandom.com/wiki/Holocron_Heist).

![](younglings.png)

#### Original Galatic Empire:*

This is where all the bad stuff starts. Initially, they had a good system for managing their vasts amount of data and an off-site backup with a very powerful firewall. However, once that firewall was breached, there was poor security inside - I mean, a dead archivist’s hand could be used to access *the entire system*, presumably as a root user. Their storage facility also relied on a rather inconvenient system for accessing data: a massive tower than required a remote-controlled tool for physical retrieval of data files. 

![](archive_joystick.png)

The tool itself required manual operation and apparently the entire facility had no backup generator to maintain secruity and functioning in case of a power loss. Incredibly, there was also no search tool. Data archives had to be *browsed* (what???). it’s really quite astonishing that anyone ever found what they needed. Options for sending out the data were also remarkably cumbersome - a satellite dish the size of a Star Destroyer has to manually turned in the correct direction to send a file out (was the Empire capable of automating anything?). I also wonder about the file compression capabilities - seriously, is there any file so large it needs a satellite dish of that size? 

![](scarif_tower.JPG)

#### The First Order:

The First Order inherits a number of problems from the original Galatic Empire, most notably insufficient backups resulting in lost information. A map to Luke Skywalker is lost, making it nigh impossible to find him. A map to Exogol had two copies ever made, one of them on a destroyed death star sitting in the middle of raging ocean? It’s amazing these were very found. Without these maps, we have no Sith and no Jedi (maybe not such a bad thing). 

![](skywalker_map.jpg)

The point is that if the Jedi had better data practices, then they might have avoided the rise of the empire. And perhaps if the Empire had better data practices, they may not undergone such a rapid downfall. 

![](death_star_wreckage.jpg)

#### What happens with good data management: 

* Secure data that can only be modified by authorised users 
* Validation of data values to prevent errors
* Data is accessible: it can be accessed in many places, by many, in formats that are easy to use 
* Stored data is easy to search and summarise 
* There are sufficient backups if something goes wrong 

#### Wait! This actually matters!

This is more than a story to amuse folks, though. Poor data management is a rampant issue across academia. I have observed that most researchers do not document their data processing in sufficient detail to recreate the process. Who else has read this statement "outliers were removed" with no details into how those outliers were eliminated or the numerical values of those "outliers"?  

From a research standpoint this means the analytical procedure is not replicable. That means someone starting with the same raw data will not obtain the same results following the described analtical procedure -- because the description was inadequate. This can also mean data are unreliable. If the orginal version of data become lost as individuals clean up the data and do not document their process, then there is no way to evaluate if the cleaning was correctly done or justified. Data loss is always a risk when files are emailed around rather than shared via a more permanent data storage solution. All of these risks become amplified when an individual leaves a research program and can no longer be reached to resolve data questions. 
  
#### Tools for better data management

Handily, many many tools exist to assist in data management. I give a bare bones outline in this [post](/post/workflow_basics/) (please read this!!). Below is an even more bare 'bare bones' outline.

One of the best solutions is to put your data in a database. This a great tool for large quantities of data that follow a regular format and are frequently updated - such as variety testing data. 

However, most agricultural researchers are not so lucky to have such structured data. At the very least, maintaining research outputs in a shared and secured location is a good start. Archiving raw versions of data is paramount. This maybe never be needed, but if it is needed, there is not replacement if those data are lost. Requiring complete documentation from all research contributors on the data set generation and processing is also good. A "codebook" is another great tool. This is a file accompanying a data set that provides the name of each column, what data are present in that column, and optionally, the units of those data and the range of values expected. If a column contains contains numeric values btweeen 0 and 100, then others will know that 980 is probably an error.

Most of the researchers I work with were trained in a different era - when data was expensive to obtain and as a result, there was considerably less data to deal with. I count myself among this group. At that time, data management tools were less relevant because we had the time to comprehensively examine a data set for errors. Furthermore, data sharing and data reuse were not widely done. But, we all now those days are long over. We are now expected to process a large quantity of data rapidly, analyse it and eventually arhive it publicaly for possible reuse by someone else. Engaging in practices that enable quality data management is essential for participation in today's research environment.

