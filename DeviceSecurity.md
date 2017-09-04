# Security on Crestron Devices #

Please don't shoot yourself in the foot and blindly enter these commands. You need to know what features you need enabled on a given project and what you can safely turn off/configure. 

Some of these commands only work on procs, some only work on touch screens, and it all depends on firmware versions you are running. But, if you want to secure your system, these commands are worth investigating/knowing about:

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

Finally, **remember that authentication is not the same thing as secure channel communications**. You may turn authentication on, but endpoints that aren't talking a secure protocol, such as SSL or Secure CIP, are vulnerable to network sniffing and MITM attacks.

## Default Open Ports on Series 3 Procs ##
<pre>
21/tcp    open  FTP
22/tcp    open  SSH
23/tcp    open  Telnet Crestron CTP console
80/tcp    open  HTTP
137/udp   open  NetBT name service
138/udp   open  NetBT datagram
443/tcp   open  HTTPS
843/tcp   open  Flash Policy server
6510/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6511/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6512/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6513/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6514/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6515/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
6516/tcp  open  (Appears to be dynamic proxy port for ActiveSync)*
41794/udp open  Crestron CIP
41794/tcp open  Crestron CIP
41795/tcp open  Crestron CTP
</pre>

*Typical ports for ActiveSync(3000-3031; 6510-6541)
