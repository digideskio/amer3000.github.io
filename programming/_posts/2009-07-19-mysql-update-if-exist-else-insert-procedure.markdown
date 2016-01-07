---
layout: post
permalinks: mysql-update-if-exist-else-insert-procedure
title: MySQL Update If Exist Else Insert Procedure
---

Are you tired of checking data in your code before inserting? Well MySQL procedures are here to rescue. This simple procedure shows how you can do that:

<code>
CREATE PROCEDURE `update_insert_user`( IN uid2 int  )
BEGIN
DECLARE last_login2 DATETIME;
SELECT `last_login` INTO last_login2 FROM `user` WHERE `uid` = uid2 LIMIT 1;
IF last_login2 IS NULL THEN
INSERT INTO `user` (`uid`,`last_login`) values (uid2, now());
ELSE
UPDATE `user` SET `last_login` = now() WHERE `uid` = uid2 LIMIT 1;
END IF;
END
</code>

You just call one line of SQL from your code, keeping your code cleaner and easier to debug.

