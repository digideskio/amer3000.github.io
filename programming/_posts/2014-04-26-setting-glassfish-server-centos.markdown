---
layout: post
permalinks: setting-glassfish-server-centos
title: Setting up Glassfish Server on CentOS
---

All these steps are based on tutorial from [http://.c2b2.co.uk/2013/06/getting-started-with-glassfish-4.html](http://.c2b2.co.uk/2013/06/getting-started-with-glassfish-4.html)



	
  1. `yum install java-1.7.0-openjdk-devel`

	
  2. Add following lines to `/etc/profile`:
`export PATH=$PATH:/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.55.x86_64/bin
export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.55.x86_64`


	
  3. Run this command to reload environment variables: `source /etc/profile`

	
  4. `wget http://download.java.net/glassfish/4.0/release/glassfish-4.0.zip`

	
  5. `unzip -d /opt/oracle glassfish-4.0.zip`

	
  6. `cd /opt/oracle/glassfish4/bin/`

	
  7. `./asadmin start-domain`

	
  8. 

    
    ./asadmin create-service
    Found the Linux Service and successfully uninstalled it.
    The Service was created successfully. Here are the details:
    Name of the service:domain1
    Type of the service:Domain
    Configuration location of the service:/etc/init.d/GlassFish_domain1
    User account that will run the service: root
    You have created the service but you need to start it yourself. Here are the most typical Linux commands of interest:* /etc/init.d/GlassFish_domain1 start
    * /etc/init.d/GlassFish_domain1 stop
    * /etc/init.d/GlassFish_domain1 restart
    For your convenience this message has also been saved to this file: /opt/oracle/glassfish4/glassfish/domains/domain1/PlatformServices.log
    Command create-service executed successfully.
    




	
  9. `./asadmin change-admin-password` . Initial admin password is blank. You need to change it to something else.

	
  10. `./asadmin --host blah.example.com --port 4848 enable-secure-admin`

	
  11. Enjoy!


