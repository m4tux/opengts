
OpenGTS tracking server from http://opengts.sourceforge.net/


Welcome to opengts docker container which installed on fedora based container .


How to use:

- install docker ( yum install docker on rpm based linux , apt-get install docker on debian based linux )
- docker pull mysql
- docker pull m4tux/opengts

Start mysql and set the root password:

docker run --name opengts_mysql -e MYSQL_ROOT_PASSWORD=GtsSecretPassword -d mysql

Start opengts and link to mysql database:

docker run -it  -p 8080:8080 -p 8022:22 --name opengts --link opengts_mysql:mysql  m4tux/opengts

After tomcat started, you can log to your machine on port 8080, for example:

http://localhost:8080 for tomcat (manager is admin, password admin)

or to opengts track application:

http://localhost:8080/track/Track (Account sysadmin is created without password).
