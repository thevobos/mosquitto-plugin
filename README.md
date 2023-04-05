
# Mosquitto Dynamic Security Plugin

Mosquitto authentication and ACL (Access control list) checking plugin. It is working based on MYSQL database.
## Configuration

#### How to install?

Download **mosquitto-auth.so** file and load .conf file as follows
```mosquitto -c mosquitto.conf```

**[Download](https://phpbolt.com/wp-content/uploads/2023/03/mosquitto-auth.zip)**

The mosquitto.conf file

```plugin path/to/mosquitto-auth.so```

#### Configure the MySQL Database

Download mosquitto.sql file and import to your mysql by phpmyadmin. Then create .env file and add database credentials.

``` 
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=mosquitto
DB_USERNAME=root
DB_PASSWORD="Pass"
```

## Documentation

Authentication is working based on MYSQL users table. This plugin is checking username and password. Add username and password in users table.

ACL: Add access details acls table.


| column  | Value  | Permission |
| ------- | ------ | ---------- |
| rw      | 1      |    READ    |
| rw      | 2      |   WRITE    |
| rw      | 4      | SUBSCRIBE  |
| rw      | 8      | UNSUBSCRIBE|

Setting up MySQL Authentication Plugin in Mosquitto MQTT Broker
The Mosquitto is an open-source message broker for the internet of things (IoT). We can easily configure the MySQL Mosquitto-auth plugin.

Configure the open-source MySQL Mosquitto-auth plugin in Linux. This mosquitto dynamic security is developed with Rust programming language.

Mosquitto-auth MySQL plugin
Mosquitto-auth plugin MySQL tables
1. Install the Mosquitto Server
Install the mosquitto from Ubuntu’s software repository.

Update the package information


sudo apt update


2. Install the mosquitto package.

sudo apt install -y mosquitto

3. Stop the mosquitto service

sudo systemctl stop mosquitto

4. Download mosquitto-auth.so file (Download)

5. Edit mosquitto.conf file

sudo vi /etc/mosquitto/mosquitto.conf

And add the following entries to the mosquitto.conf file.

plugin /path/to/mosquitto_auth.so

#listener 1883
The mosquitto allows remote connections by adding a listener port.

Configure MySQL Database
Download the mosquitto.sql file and import it to your MySQL by PHPMyAdmin. Then create a .env file and add database credentials.

DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=mosquitto
DB_USERNAME=root
DB_PASSWORD="Pass"
Move .env file to /

mv /path/to/.env /.env

Start the mosquitto server

sudo systemctl start mosquitto


