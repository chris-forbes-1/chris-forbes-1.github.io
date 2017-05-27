---
layout: post
title: "Diff two directories in powershell"
date: 2017-05-27
excerpt: "How to get a diff of two directories in powershell"
project: false
tag: 
- powershell
- windows
- file_diff

comments: true
---
Whilst testing a jenkins deployment I wanted to make sure that the folder I'd zipped and shipped from our jenkins host to the new windows server
box was actually correct. But I couldn't for the life of me think how to do this on a windows machine! Well problem solved:
``` powershell 
Compare-Object -ReferenceObject (Get-ChildItem -r -dir <path to your existing directory>) -DifferenceObject (Get-ChildItem -r -dir <path to your new directory>)
```

Short hand you can also do:

```powershell 
Compare-Object -ReferenceObject (gci -r -dir <path1>) -DifferenceObject (gci -r -dir <path2>)
```