# Liquibase

**Build new image for mysql**
```bash
docker build . -t liquibase/liquibase-mysql
```

**Runtime Example**
```bash
docker run -e INSTALL_MYSQL=true liquibase/liquibase update
```

__Using a properties file__
```
classpath: /liquibase/changelog
url: jdbc:postgresql://<IP OR HOSTNAME>:5432/<DATABASE>?currentSchema=<SCHEMA NAME>
changeLogFile: changelog.xml
username: <USERNAME>
password: <PASSWORD>
liquibaseProLicenseKey=<PASTE LB PRO LICENSE KEY HERE> 
```

**Runtime Example using properties**
```bash
docker run --rm -v <PATH TO CHANGELOG DIR>:/liquibase/changelog liquibase/liquibase --defaultsFile=liquibase.docker.properties update
```