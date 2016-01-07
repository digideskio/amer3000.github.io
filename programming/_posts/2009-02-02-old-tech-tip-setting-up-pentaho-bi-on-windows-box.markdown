---
layout: post
permalinks: old-tech-tip-setting-up-pentaho-bi-on-windows-box
title: Setting Up Pentaho BI on Windows Box

---

_I am not sure if this works anymore or not. I don't use Pentaho now but this post seems popular, so leaving it here for now. Contact me if this is incorrect and needs to be corrected or taken down._



	
  1. Download Pentaho BI Pre-Configured Installation from http://www.pentaho.org/download/ga.php

	
  2. Install JDK5.

	
  3. Open **C:\pentaho-demo\pentaho-solutions\system\publisher_config.xml**. Add a password for publishing reports.

	
  4. Delete all folders except **reporting** under **C:\pentaho-demo\pentaho-solutions\samples**.

	
  5. Delete all .xaction and .properties files under reporting.

	
  6. Copy JDBC driver for your database under **C:\pentaho-demo\jboss\server\default\lib**. I used Oracle 10g driver, it is called ojdbc.jar.

	
  7. Edit .jsp file to change the look of default Pentaho website under **C:\pentaho-demo\jboss\server\default\deploy\pentaho.war\jsp**.

	
  8. Add path to your JDK in **start-pentaho.bat** located under C:\pentaho-demo. For example, **set JAVA_HOME=C:\Program Files\Java\jdk1.5.0_11**

	
  9. Double click on start-pentaho.bat.

	
  10. Open **C:\pentaho-demo\jboss\server\default\deploy\pentaho.war\WEB-INF\web.xml**. Search for base-url and add your server's ip.

	
  11. Now you should be able to publish reports to Pentaho using Report Wizard or Report Designer.

	
  12. Once you publish report, you will need to go to **C:\pentaho-demo\jboss\server\default\deplo**y and open newly created data source file named something like ???????-ds.xml.

	
  13. If your database is Oracle you will need to change driver class property to **<driver-class>oracle.jdbc.driver.OracleDriver</driver-class>**

	
  14. And your newly published report should be accessible via Pentaho now.


