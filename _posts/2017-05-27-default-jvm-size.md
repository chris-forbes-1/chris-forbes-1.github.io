---
layout: post
title:  "Default JVM memory size"
date:   2017-05-27
excerpt: "Finding the default amount of memory a JVM will grab on startup."
tag:
- java 
- jvm
- linux
- command
comments: true
---
One of our centos servers had started to throw the world famous
```java
Java.lang.OutOfMemoryException
```
We decided to find out initially how much memory it was taking on startup and came up with this:
``` bash
 java -XX:+PrintFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'
```
[I found this a particularly useful read if you dont know much about java memory management](https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/) 
