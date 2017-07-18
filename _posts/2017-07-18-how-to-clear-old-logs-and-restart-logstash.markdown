---
title: "How to clear logs and restart Logstash"
layout: post
date: 2017-07-18 19:09
tag: [sysadmin, elk, tidbits, Storm]
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
description: "How to clear logs from where Logstash stores them and restart when Logstash crashes due to backed up logs"
category: blog
author: pasankarunaratne
externalLink: false
---
I run an [Apache Storm](http://storm.apache.org) cluster and use the [ELK Stack](https://www.elastic.co/webinars/introduction-elk-stack) to preserve my sanity when analysing logs from different machines on the cluster. 

![ELK Stack on Apache Storm]({{ site.url }}/assets/images/logstash-clear-restart-post/kibana-capture-1.png)

It's pretty cool and has saved me from pulling my hair out grepping and tailing log files from a number of machines. 

However, when ingesting data at very high rates Logstash sometimes fails and stops listening on port 5044. Doing a simple restart just results in Logstash trying to process the old logs that it is yet to index, which slows it down to a crawl yet again. 

The procedure to clear out the logs from Logstash and start afresh strangely seems to not be specified in the documentation. Hence this post.

Logstash stores the logs it reads in the folder ```/var/log/logstash``` (on Ubuntu 16.04) in the form of ```logstash.stdout.*``` files. 

Delete the ```logstash.stdout.*``` files in this location, and then restart logstash using 

 ```sudo systemctl restart logstash``` 

Do a ```sudo systemctl status logstash``` for good measure. 

---
