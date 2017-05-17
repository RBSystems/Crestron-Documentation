# Crestron Security #

Please don't shoot yourself in the foot and blindly enter these commands. You need to know what features you need enabled on a given project and what you can safely turn off/configure. 

Some commands of these commands only work on procs, some only work on touch screens, and it all depends on firmware versions you are running. But, if you want to secure your system, these commands are worth investigating/knowing about:

- SETPASSWORDRULE -LENGTH:## -ALL
- AUTH ON
- WEBSERVER OFF
- TELNETPORT OFF
- FTPSERVER OFF
- CIPHER STRONG
- SECUREGATEWAYMODE SECUREEXT
- SETLOGINATTEMPTS 2
- SETLOCKOUTTIME 48
- AUDITLOGGING ON ALL
- SETLOGOFFIDLETIME 10
- ENABLEFEATURE CLOUDCLIENT OFF
- ENABLEFEATURE RFGATEWAY OFF
- ENABLEFEATURE SNMP OFF
- SSL NOVERIFY
- SETCSAUTHENTICATION -N:Username -P:Password
- SIPENABLE OFF
- ENTERSETUPSEQ OFF

Finally, remember that authentication is not the same thing as secure channel communications. 