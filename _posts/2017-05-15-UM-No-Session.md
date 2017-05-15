---
layout: post
title: Usage Meter 3.5 No Session is bound to current thread error 
---

The following exception appears immediately after UI login 

```
Message: java.lang.RuntimeException: No session is bound to current thread, 
a session must be created via Session.create 
and bound to the thread via 'work' or 'bindToCurrentThread'
Usually this error occurs when a statement is executed outside of a transaction/inTrasaction block
```


### Solution: 

The cause may be an error in the UM default.props configuration file.

Remove any parital comment lines, for example

```
sessionTimeout=7200000  # new timeout
```

should be changed to a separate comment and property line.

```
# new timeout
sessionTimeout=7200000 
```
