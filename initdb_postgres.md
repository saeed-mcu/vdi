## Generate initdb.sql script
```
docker run --rm registry.ferdowsi.cloud/guacamole/guacamole:1.4.0  /opt/guacamole/bin/initdb.sh --postgres > initdb.sql
```
## Copy script inside container
```
docker cp ./initdb.sql guacamole_postgres:/home/initdb.sql
```
## Execute script in container
```
docker exec  -it guacamole_postgres psql -U guacamole_user -d guacamole_db -f /home/initdb.sql
```

You can access the web login screen for Guacamole from computers in the network via http://****:8080/guacamole (Where the **** is the IP address of your Amahi server). The default user name/password is guacadmin/guacadmin. You can change your password by editing your own user in the administration screen.
