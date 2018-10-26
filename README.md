# docker-phpipam

phpIPAM is an open-source web IP address management application in use by Vopak. IP address management application.

## How to use this Docker image

### Mysql

### Phpipam 

### Specific integration (HTTPS, multi-host containers, etc.)

### Configuration 

* Browse to `http://<ip>[:<specific_port>]/install/`
* Step 1 : 
* Step 2 : Re-Enter connection information
* Note
* Step 3 : Configure the admin user password

### Docker compose 

You can also create an all-in-one YAML deployment descriptor with Docker compose for testing on local environment, like this:

```yaml
version: '3'

services:
  ipam:
    depends_on:

    image: vortexict/phpipam
    environment:
      - MYSQL_USER=root
      - PASSWORD=<my-secret-pw>
      - MYSQL_HOST=<IP number of MySQL (AWS RDS) server>
      - MYSQL_DB=phpipam
      - MYSQL_PORT=3306
    ports:
      - "80:80"
volumes:
  db_data:
```

And next :

```bash 
$ docker-compose up -d
```

### Notes

phpIPAM is under heavy development by the developer. 
phpIPAM is developed and maintained by Miha Petkovsek, released under the GPL v3 license.
project source: [here](https://github.com/phpipam/phpipam)
project source releases: [here](https://github.com/phpipam/phpipam/releases)
Learn more on [phpIPAM homepage](http://phpipam.net) 

To upgrade the release version, just change the `PHPIPAM_VERSION` environment variable to the target release in the docker file
