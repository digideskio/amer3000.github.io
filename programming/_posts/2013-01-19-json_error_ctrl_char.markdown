---
layout: post
permalinks: json_error_ctrl_char
title: JSON_ERROR_CTRL_CHAR
---

I was using **mcrypt** to encrypt **json_encoded** data.

On other side, mycrypt was able to decrpyt data but **json_decode** was not working. It would throw **JSON_ERROR_CTRL_CHAR** error.

However, without mcrypt, json_decode worked flawlessly.

After some trial and error, I found that applying **trim** function after decrypting data would let me use json_decode without any issues.
