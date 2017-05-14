# docker-compose_nginx-php-mysq

    Step 1:
         Make a empty folder and download the docker-compose.yml in it.

    Step 2:
        Modify the docker-compose.yml(input your IP Address).
        
    Step 3:
        Run!!!


### Run a php debuger server and MySQL server:
~~~
docker-compose up
~~~
or
~~~
docker-compose up -d  # in the background
~~~

### How to config the file 
~~~
services:
  web:
    image: baofengyv/nginx-php-xdebug
    ports:
      - "80:80"
    environment:
      - XDEBUG_REMOTE_HOST=192.168.100.2     <<<------- modify this!!! 
    volumes:
      # Path on the host, relative to the Compose file
      - ./NGINX_ROOT:/var/www/html    

  mysql:
    image: mysql
    ports:
      - "3306:3306"
    environment:
      - MYSQL_ROOT_PASSWORD=root
    volumes:
      # Path to store DATA
      - ./MYSQL_DATA:/var/lib/mysql
~~~
