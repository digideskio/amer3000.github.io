---
layout: post
permalinks: ssh_exchange_identification-connection-closed-by-remote-host
title: 'ssh_exchange_identification: Connection closed by remote host'
---

I tried to login to my server tonight but kept getting following error message:

    
    ssh_exchange_identification: Connection closed by remote host


The fix was simple, at least if you have access to server via cPanel. Just **restart sshd service** via cPanel/WHM.
