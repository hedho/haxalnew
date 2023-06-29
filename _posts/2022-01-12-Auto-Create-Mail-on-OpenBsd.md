---
layout: post
title:  "Create email in a single command on OpenBSD"
tags: OpenBSD, Mail
mathjax: on
---

# Before you're using the script you follow thise steps:

----------------------------------------------------------------------------------------------------------
Setup ur password:
## smtpctl encrypt urpassword
----------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------
Copy the output similar to:

## $2b$10$84fg5Dn9z.uTsEXSJ1JcoOi99vPtbF.D1e0cTHRgOATFgFnzvssCi
----------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------
And afterwards run this command to use the script:
## Note if you're using it as Super user you must add "doas"
----------------------------------------------------------------------------------------------------------
## doas bash newmail user whateverdomain.tld $2b$10$84fg5Dn9z.uTsEXSJ1JcoOi99vPtbF.D1e0cTHRgOATFgFnzvssCi
----------------------------------------------------------------------------------------------------------

And you're email will be created.

Thank you!

> #!/bin/bash

>echo $1: $1@$2 >> /etc/mail/aliases
>echo $1@$2  vmail >> /etc/mail/virtuals
>echo $1@$2:$3::::::userdb_quota_rule=*:storage=1G >> /etc/mail/passwd
>rcctl restart smtpd
>rcctl restart dovecot

