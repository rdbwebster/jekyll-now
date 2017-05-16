---
layout: post
title: Usage Meter 3.5 crypto.BadPaddingException error 
---

The following exception appears on the manage page.

```
Message: javax.crypto.BadPaddingException: Given final block not properly padded
```


### Solution: 

The cause may be an portal password configured on the Provider page,
If the password was encrypted on a different appliance.
This can happen in some cases after a UM migration or db import.

Login to the UM appliance and start a Postgres psql session
Set the existing portalPassword to an empty string using the following command.

```
update "Provider" set "portalPassword" = '';
```

