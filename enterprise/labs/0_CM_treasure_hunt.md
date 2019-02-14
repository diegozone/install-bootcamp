# What is ubertask optimization?

The Cloudera manager help and documentation doesn't explain clearly the meaning.

The best answer, I found, comes from stackoverflow website 
https://stackoverflow.com/questions/30284237/what-is-the-purpose-of-uber-mode-in-hadoop


# Where in CM is the Kerberos Security Realm value displayed?

Administration\security\Kerberos Credential\Settings 
property "Kerberos Security Realm"

# Which CDH service(s) host a property for enabling Kerberos authentication

Kerberos controls the authentication for every services; it prevents the unauthorized access to the data and the services. 
Once enabled , it forces the authentication for the all services in cluster without exceptions.
The answer is :" Only the cluster itself has this property "


# How do you upgrade the CM agents

you have to follow the official documentation
by setting the current version ,OS , database used as repository , if Navigator is present and the target version.
The link
https://www.cloudera.com/documentation/enterprise/upgrade/topics/ug_cm_upgrade_before.html#cm_upgrade_before

# Give the tsquery statement used to chart Hue's CPU utilization?

In Cloudera Manager on clustername\hue page,locate the chart "CPU Cores Used", click on the gear in the top right corner and select the "open chart builder".
you can see the query
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue

# Name all the roles that make up the Hive service
In cloudera manager ,Open the clustername\hive\instance page
you can see the list of installed instance .

# What steps must be completed before integrating Cloudera Manager with Kerberos?
retreive the necessary information and user accesses :
1.   information about the installation nodes, Cloduera versions , operating system , jdk version (not all jkds support AES-256)
2.   if a kerberos server(MS AD , MIT KDC, FreeIPA or Redhat IDM) is already installed and is possible to use.
3.   kerberos server info (a principal to access  , server name , port, encryptition algorithm used ) 
4.   the username to access to Cloudera Manager with the "Full Administrator" role
5.   the OS root access to the cluster ,If the operating system is not configured via ldap at the same kerberos repository 
 
