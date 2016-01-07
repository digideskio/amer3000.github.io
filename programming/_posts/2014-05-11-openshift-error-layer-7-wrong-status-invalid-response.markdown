---
layout: post
permalinks: openshift-error-layer-7-wrong-status-invalid-response
title: 'OpenShift Error: Layer 7 Wrong Status, Invalid Response'
---

I have been playing with [OpenShift](https://www.openshift.com/) for past several hours. It looks great. But a while back I started to get 503 Internal Server error.

When I checked logs using rhc tail , I saw this error: **Layer 7 Wrong Status, Invalid Response 404.**

I spent an hour or so troubleshooting. Turns out the issue was Netbeans had added srcmainwebappWEB-INFjboss-web.xml when I ran the application locally on my machine. I committed this file, thinking I might need it. **Deleting it from repo and repushing, fixed the issue.**
