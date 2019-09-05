## EasyWay to Run PHP Fast-cgi on windows via Caddy Web Server

There are lots of guides for running php on linux via CADDY SERVER, there are close to nil guide on windows.

The Configuration file includes-
> localhost:2020

This Line
> on startup c:\php7\php-cgi.exe -b 9999 &

Tells caddy server to run a  fastcgi on localhost port 9999. 
Note: Running php this way means, that the php-cgi process will be started/shutdown automatically when caddy is started /stopped.  

### Running Command on Terminal

You then run command on your terminal by doing this
> ./caddy.exe -conf ./Caddyfile

### Run this as a windows service 

Easiest way is to use this software tool nssm from https://nssm.cc

 
### Test

So far this has been tested on the following :
 1. Windows Azure Server
 2. Amazon Ec2
 3. Windows 10
 I believe it should run with other windows server.


 ### Notes
 
 1. Ensure the "&" is added, as it ensures the instruction does not block subsequent command including cadd from continuing.
 2. Keep in mind that "./caddy.exe", "c:\php7\php-cgi.exe", "./Caddyfile" are path to "caddy.exe, php-cgi.exe and Caddyfile" on my server. Remember to use your own path location.
 3. The Caddyfile file can be named whatever.anyext. The idiomatic Caddy way is to name it "Caddyfile" without an extension.
 4. Its important to note that there is no "php-fpm" for windows yet. Many of the guide you see online claiming to be php-fpm for windows are wrong. They are cgis.


 ## Source

 [4]. http://php.net/manual/en/install.fpm.php#121725
