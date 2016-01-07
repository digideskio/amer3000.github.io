---
layout: post
permalinks: undocumented-codeigniter-green-egg-media
title: CodeIgniter Out Of Memory Error
---

<blockquote>Query Saving is a feature of CI’s database class that stores the results of every query in memory until the controller is finished executing. As it turns out, in version 1.6.0, the ability to turn this off was added. The addition of the save_queries variable is listed in the Change Log, but as of the latest release of 2.0.0 last week, it still hasn’t made the documentation.
</blockquote>



    
    $this->db->save_queries = FALSE;




via [Undocumented CodeIgniter | Green Egg Media](http://www.greeneggmedia.com//entry/undocumented-codeigniter).


One thing to note is that disabling save_query would disable some other Database class functions like last_query(). So it is not just used by profiler.
