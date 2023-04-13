```
rpm -ivh https://repo.mongodb.org/yum/amazon/2013.03/mongodb-org/4.0/x86_64/RPMS/mongodb-org-shell-4.0.25-1.amzn1.x86_64.rpm --nodeps --force

mongo --port 27017 --host 10.0.12.3  --authenticationDatabase "admin" -u "root" -p "password"


mongo --port 27017 --host 10.0.12.3  --authenticationDatabase "admin" -u "root" -p "password"



docker run -d --restart=always -p 27017:27017 --name mymongo -v /data/db:/data/db -d mongo

docker exec -it mymongo /bin/bash
```