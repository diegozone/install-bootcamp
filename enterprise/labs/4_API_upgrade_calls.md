# API version

curl -u diegozone:cloudera http://localhost:7180/api/version

```
v19
```

# CM version

curl -u diegozone:cloudera http://localhost:7180/api/v19/cm/version
```
{
    "version": "5.16.1",
    "buildUser": "jenkins",
    "buildTimestamp": "20181120-1809",
    "gitHash": "6a13b87a6fcdf4afad6d4474a68a9434b24d6c67",
    "snapshot": false
}
```
# List all CM users

curl -u diegozone:cloudera http://localhost:7180/api/v19/users
```
{
    "items": [
        {
            "name": "admin",
            "roles": [
                "ROLE_LIMITED"
            ]
        },
        {
            "name": "diegozone",
            "roles": [
                "ROLE_ADMIN"
            ]
        },
        {
            "name": "minotaur",
            "roles": [
                "ROLE_CONFIGURATOR"
            ]
        }
    ]
}
```
# Report the database server in use by CM

curl -u diegozone:cloudera http://localhost:7180/api/v19/cm/scmDbInfo
```
{
    "scmDbType": "MYSQL",
    "embeddedDbUsed": false
}
```
