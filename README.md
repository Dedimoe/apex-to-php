# apex-to-php
Connection between oracle apex to php

1. On php side: Activate oci8

I assume we already install bitnami lamp stack.

Enable the oci8 module in the /opt/bitnami/php/etc/php.ini file.

Check if the module is active:
```
/opt/bitnami/php/bin/php -m
```
If not active, download the Oracle InstantClient Basic package for your platform from the Oracle website : http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html.

Extract the package contents in your home folder.

Add the following environment variable to the end of your 

/opt/bitnami/scripts/setenv.sh file:
```
 LD_LIBRARY_PATH=/home/bitnami/instantclient_11_2:$LD_LIBRARY_PATH
 export LD_LIBRARY_PATH
```
Restart the servers:
```
sudo /opt/bitnami/ctlscript.sh restart
```
Check again if the module is active:
```
/opt/bitnami/php/bin/php -m
```

2. On apex side:

