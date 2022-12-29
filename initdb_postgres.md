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

