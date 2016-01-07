---
layout: post
permalinks: codeigniter-creating-a-new-session-with-each-page-load
title: CodeIgniter Creates a New Session with Each Page Load
---

Just spent 3 hours debugging a session bug in my webapp. CodeIginter was creating a brand new session with each page load. The issue was a misconfiguration with my config file.

**Fix was simple, in `/application/config/config.php`, make sure correct domain is set for `$config['cookie_domain']`.**
